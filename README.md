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

2. Install stuff:
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

## How it works

The tool has three main parts:
- Planner: Figures out what needs to be done
- Architect: Plans the files and structure
- Coder: Actually writes the code

It uses a graph to manage the workflow, so everything happens in the right order.

## Requirements

- Python 3.13 or newer
- A Google AI API key
- That's it!

## Files

- `graph.py` - Main script
- `schema.py` - Data models
- `prompt.py` - AI prompts
- `tools.py` - Helper functions
- `graph_visualization.ipynb` - Notebook to see the workflow graph

## Notes

This is a basic version. It might not handle everything perfectly, but it's a good starting point for AI-assisted coding.

3. **Set up environment variables**
   ```bash
   cp .env.example .env
   ```
   
   Edit `.env` and add your API keys:
   ```env
   GOOGLE_API_KEY=your_google_api_key_here
   GROQ_API_KEY=your_groq_api_key_here  # Optional
   ```

## 🎯 Usage

### Basic Usage

Run the main application:
```bash
python main.py
```

Enter your prompt when prompted:
```
Enter your prompt: Create a simple web scraper for news articles
```

### Interactive Mode

The application will:
1. **Plan**: Analyze your request and create a high-level plan
2. **Architect**: Break down the plan into specific implementation steps
3. **Code**: Implement each step by creating/modifying files
4. **Output**: Generate the complete project in `generated_project/` directory

### Example Prompts

- "Create a REST API with FastAPI and SQLAlchemy"
- "Build a data visualization dashboard with Streamlit"
- "Implement a machine learning pipeline for image classification"
- "Create a web scraper for e-commerce product data"

## 📁 Project Structure

```
CursorClone/
├── main.py                 # Main application entry point
├── graph.py                # LangGraph workflow implementation
├── tools.py                # File operation tools and utilities
├── schema.py               # Pydantic models for data structures
├── prompt.py               # AI prompt templates
├── graph_visualization.ipynb  # Jupyter notebook for workflow visualization
├── pyproject.toml          # Project dependencies and configuration
├── .env                    # Environment variables (not tracked)
├── .gitignore             # Git ignore rules
└── generated_project/      # Output directory for generated code
```

## 🔧 Configuration

### Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `GOOGLE_API_KEY` | Google AI API key for Gemini | Yes |
| `GROQ_API_KEY` | Groq API key (alternative LLM) | No |

### Model Configuration

The default configuration uses:
- **Model**: `gemini-2.5-flash`
- **Recursion Limit**: 50 steps
- **Debug Mode**: Enabled

## 🛠️ Development

### Adding New Tools

1. Define new tools in `tools.py`:
   ```python
   @tool
   def your_new_tool(param: str) -> str:
       """Description of what the tool does."""
       # Implementation
       return result
   ```

2. Add to the coder agent tools list in `graph.py`

### Customizing Prompts

Edit `prompt.py` to modify agent behavior:
- `PlannerPrompt`: Controls planning agent behavior
- `ARCHITECT_PROMPT`: Controls architecture agent behavior  
- `CODER_SYSTEM_PROMPT`: Controls coding agent behavior

## 📊 Visualization

Use the Jupyter notebook to visualize the workflow:
```bash
jupyter notebook graph_visualization.ipynb
```

## 🔒 Security

- **File Safety**: All file operations are restricted to the project root
- **Path Validation**: Prevents directory traversal attacks
- **Environment Isolation**: Sensitive data stored in `.env` (not tracked)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [LangGraph](https://github.com/langchain-ai/langgraph) for the workflow framework
- [Google Gemini](https://ai.google.dev/) for the AI capabilities
- [LangChain](https://github.com/langchain-ai/langchain) for the LLM integration

## 📞 Support

If you encounter any issues or have questions:

1. Check the [Issues](https://github.com/samakshmehra/CursorClone/issues) page
2. Create a new issue with detailed information
3. Include error messages and steps to reproduce

---

**Happy Coding! 🎉**
