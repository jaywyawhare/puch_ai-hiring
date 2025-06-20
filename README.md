# PuchAI Hiring Challenge - Enhanced MCP Server Implementation

This repository contains my submission for the PuchAI hiring challenge. While the core requirement was to implement a simple MCP server with resume functionality, I decided to extend it into a comprehensive backend implementation showcasing additional capabilities.

## 🎯 Base Requirements
- Implement MCP server with resume tool
- Return developer's resume in markdown format
- Include validation tool required by Puch AI system

## 🚀 Extended Implementation   
I went beyond the basic requirements to demonstrate my expertise by implementing:

### Additional Tools
- **Web Tools**: fetch and search functionality
- **Railway Tools**: Live train data integration
- **Music Tools**: YouTube and streaming platform integration
- **Weather Tools**: Real-time weather data by location
- **Academic Tools**: arXiv paper search and retrieval

### 🛠️ Available Tools

#### Core Tools
- **`resume()`** - Serves the developer's resume in markdown format
- **`validate()`** - Validation tool required by Puch AI system
- **`get_help_menu()`** - Comprehensive help menu for all available tools
- **`arxiv(query, max_results)`** - Search and fetch academic papers from arXiv.org

#### Web Tools
- **`fetch(url, max_length, start_index, raw)`** - Fetch and process web content with smart HTML-to-markdown conversion
- **`search_information_on_internet(query, max_results)`** - Search for information using DuckDuckGo API

#### Railway Tools (🔴 Live Data from Indian Railways)
- **`get_live_train_status(train_number, date)`** - Get detailed real-time train information from erail.in
- **`get_trains_between_stations(from_station, to_station, date)`** - Find trains between stations with live data
- **`get_pnr_status_tool(pnr_number)`** - Check PNR booking status with real passenger details
- **`get_train_schedule_tool(train_number)`** - Get complete train route with all station stops  
- **`get_station_live_status(station_code)`** - Get live status of all trains at a station

#### Music Tools (🔴 Live Data from Multiple Platforms + YouTube Streaming)
- **`get_song_name_links(song_name, artist)`** - Get real links to songs on streaming platforms
- **`get_music_recommendations(genre, mood, artist)`** - Get recommendations from live music APIs  
- **`get_youtube_music_stream(video_url, quality)`** - Extract audio stream URLs from YouTube videos
- **`search_and_stream_music(query, include_streams)`** - Search YouTube and get streaming information
- **`download_youtube_audio(video_url, output_format)`** - Download audio from YouTube videos

**🎵 YouTube Music Streaming Features:**
- **yt-dlp Integration**: High-quality audio extraction from YouTube
- **ffmpeg Processing**: Professional audio format conversion
- **Stream URL Extraction**: Direct audio streaming without downloads
- **Multi-Format Support**: MP3, AAC, WebM, and more
- **Quality Selection**: Choose audio quality for streaming/download
- **Platform Integration**: Works with YouTube, YouTube Music, and other platforms

#### Weather Tools (🔴 Live Data from OpenWeatherMap)
- **`get_weather(location, units)`** - Get current weather conditions for any location

#### Academic Tools (🔴 Live Data from arXiv.org)
- **`search_arxiv_papers(query, max_results, include_abstracts)`** - Search academic papers with advanced query support
- **`get_arxiv_paper(paper_id)`** - Get detailed information about specific papers
- Advanced query syntax support (e.g., `ti:"neural networks" AND au:"hinton"`)
- Real-time data from arXiv.org API with proper rate limiting
- Support for multiple categories and cross-references

#### Hacker News Tools (🔴 Live Data from HN API)
- **`get_hn_stories(story_type, num_stories)`** - Get stories by type (top/new/ask/show)
- **`search_hn_stories(query, num_results)`** - Search HN stories by keyword
- **`get_hn_user(username, num_stories)`** - Get user info and recent submissions
- **`get_item_details(item_id)`** - Get detailed story/comment information
- Real-time data from official HN Algolia API
- Support for story details, comments, and user profiles

Features:
- Live story feeds (top, new, ask, show)
- Full-text search capabilities
- User profiles and submissions
- Comment threading and nesting
- Story points and timestamps
- Direct links to HN discussions

### 🔧 Technical Features

- **Real API Integration**: Uses live data from erail.in for accurate railway information
- **YouTube Music Streaming**: yt-dlp + ffmpeg integration for high-quality audio streaming
- **Smart Content Processing**: HTML to markdown conversion for web content  
- **Multi-Platform Music Search**: Integration with Spotify, YouTube, Apple Music, and more
- **Comprehensive Error Handling**: Robust error management across all tools
- **Bearer Token Authentication**: Secure API access with token-based auth
- **Production Ready**: Comprehensive logging, error handling, and deployment guides

## 🚀 Quick Start

### Prerequisites
- Python 3.11+
- Git
- ffmpeg (for YouTube music streaming)

**Installing ffmpeg:**
```bash
# Ubuntu/Debian
sudo apt install ffmpeg

# macOS (with Homebrew)
brew install ffmpeg

# Arch Linux
yay -S ffmpeg

# Windows
Download from https://ffmpeg.org/download.html
Or use Chocolatey: choco install ffmpeg
```

### Installation

1. **Clone the repository:**
```bash
git clone https://github.com/jaywyawhare/PuchAI-Hiring-Challenge
cd PuchAI-Hiring-Challenge
```

2. **Create and activate a Python virtual environment:**
```bash
python3.11 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install dependencies:**
```bash
pip install -r requirements.txt
```

4. **Set up environment variables:**
```bash
cp .env.example .env # Edit .env with your actual values
```

Required environment variables:
```bash
TOKEN=your_bearer_token_here
MY_NUMBER=your_phone_number_here
```

### Running the Server

```bash
python main.py
```

The server will run on `http://0.0.0.0:8085` 
Its better to hook it up with vscode mcp server and use the chat interface to interact with the server.

## References

- [Puch AI Challenge Announcement](https://x.com/puch_ai/status/1934600752007364906)
- [Challenge Gist](https://gist.github.com/ArjitJ/cc7356bff1f782c03bf59a4f65a9d2d6)
- [FastMCP Documentation](https://github.com/jlowin/fastmcp)
- [MCP Protocol Specification](https://github.com/modelcontextprotocol/python-sdk)

## License

This project is licensed under the DBaJ-NC-CFL [License](./LICENCE.md).