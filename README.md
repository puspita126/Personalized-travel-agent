# AI Travel Agent

AI Travel Agent is a Streamlit application that helps users plan trips with an AI-powered assistant. It can understand a natural-language travel request, search for flight and hotel options, summarize the results, and optionally send the travel information by email.

The project uses LangGraph to manage the agent workflow, LangChain/OpenAI for language model interaction, SerpAPI for travel search data, and SendGrid for email delivery.

## Features

- Natural-language trip planning through a simple Streamlit interface
- Flight search support using Google Flights data through SerpAPI
- Hotel search support using Google Hotels data through SerpAPI
- LangGraph-based agent flow with stateful execution
- Optional email delivery for generated travel information
- Environment-based configuration for API keys and email settings

## Tech Stack

- Python 3.11+
- Streamlit
- LangGraph
- LangChain
- OpenAI
- SerpAPI
- SendGrid
- Poetry

## Project Structure

```text
.
├── agents/
│   ├── agent.py
│   └── tools/
│       ├── flights_finder.py
│       └── hotels_finder.py
├── images/
│   └── ai-travel.png
├── app.py
├── pyproject.toml
├── poetry.lock
└── README.md
```

## Requirements

Before running the app, make sure you have:

- Python 3.11 or newer
- Poetry installed
- API keys for OpenAI, SerpAPI, and SendGrid

## Setup

Clone the repository:

```bash
git clone git@github.com:puspita126/Personalized-travel-agent.git
cd Personalized-travel-agent
```

Install dependencies:

```bash
poetry install --sync
```

Activate the virtual environment:

```bash
poetry shell
```

## Environment Variables

Create a `.env` file in the project root:

```bash
touch .env
```

Add the following values:

```env
OPENAI_API_KEY=your_openai_api_key
SERPAPI_API_KEY=your_serpapi_api_key
SENDGRID_API_KEY=your_sendgrid_api_key

LANGCHAIN_API_KEY=your_langchain_api_key
LANGCHAIN_TRACING_V2=true
LANGCHAIN_PROJECT=ai_travel_agent
```

The LangChain variables are optional unless you want tracing and observability enabled.

## Running the App

Start the Streamlit app:

```bash
streamlit run app.py
```

Then open the local Streamlit URL shown in the terminal.

## Example Query

```text
I want to travel from Madrid to Amsterdam from October 1 to October 7. Find flights and 4-star hotels.
```

The app will process the request and return travel information with relevant flight and hotel options. After results are generated, you can choose whether to send the information by email.

## Email Flow

When email sending is enabled from the app interface, the user provides:

- Sender email
- Receiver email
- Email subject

The app then uses SendGrid to deliver the generated travel information.

## Notes

- Travel data is fetched through SerpAPI integrations for Google Flights and Google Hotels.
- Search results depend on API availability, query clarity, and the configured API keys.
- This application is intended as an AI travel planning assistant and does not complete bookings directly.

## Author

Puspita Das

## License

This project is distributed under the MIT License. See the `LICENSE` file for details.
