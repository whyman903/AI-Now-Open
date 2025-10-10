# AI-Now

A content aggregation platform for AI research news, papers, and updates from major labs and institutions. 

*initial rendering may take ~ 2 mins*

**Live Demo:** [https://ai-now.vercel.app](https://ai-now.vercel.app)

## Overview

AI-Now automatically collects and aggregates content from top AI labs, research papers, interesting Youtube Videos, and other AI-related content. The system uses a combination of RSS feeds and custom web scrapers to pull content, then normalizes and deduplicates it into a unified feed.

Built with a React frontend and FastAPI backend, deployed on Vercel and Render respectively.

## Features

- Automated content aggregation from multiple sources (RSS, YouTube, web scraping)
- Agentic information retrieval and insight synthesis
- Real-time updates with concurrent processing 
- Advanced filtering by lab, content type, and keywords
- Dark/light theme support
- Analytics tracking (views, clicks, engagement)
- Headless Chrome scraping
- Intelligent deduplication and URL canonicalization


## Tech Stack

**Frontend:**
- React 18 + TypeScript
- Vite for builds
- TanStack Query for data fetching
- Tailwind CSS + Radix UI
- Framer Motion for animations

**Backend:**
- FastAPI (async Python)
- PostgreSQL + SQLAlchemy
- Selenium for web scraping
- BeautifulSoup for HTML parsing
- httpx for async HTTP requests
- Alembic for migrations

**Deployment:**
- Frontend: Vercel
- Backend: Render
- Database: PostgreSQL (Render managed)

## Architecture

The aggregation pipeline runs concurrently across all sources:

1. **RSS Feeds** - Standard feed parsing with feedparser
2. **YouTube Channels** - API-based video fetching
3. **Web Scrapers** - Selenium-based scrapers for sites without feeds

Each source returns normalized data (title, URL, date, thumbnail, metadata) which flows through a deduplication and enrichment pipeline before database persistence.
