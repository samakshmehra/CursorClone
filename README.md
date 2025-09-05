# Cursor Clone

A simple AI tool that helps generate code based on your prompts. It uses LangGraph and Google's Gemini to plan, design, and build code automatically.

## What it does

- Takes your description of what you want to build
- Plans out the steps needed
- Creates the code files for you
- Uses AI agents to handle different parts of the work

## Quick Start

1. Clone this repo:
   ```bash
   git clone https://github.com/samakshmehra/CursorClone.git
   cd CursorClone
   ```

2. Install dependencies:
   ```bash
   pip install -e .
   ```

3. Set up your API key in a .env file:
   ```
   GOOGLE_API_KEY=your_key_here
   ```

4. Run it:
   ```bash
   python graph.py
   ```

## Requirements

- Python 3.13 or newer
- A Google AI API key

## Files

- `graph.py` - Main script
- `schema.py` - Data models
- `prompt.py` - AI prompts
- `tools.py` - Helper functions

## Notes

This is a basic version. It might not handle everything perfectly, but it's a good starting point for AI-assisted coding.
