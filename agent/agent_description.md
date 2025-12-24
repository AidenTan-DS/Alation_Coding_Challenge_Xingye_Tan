# HR AI Agent

## Access
**URL**: https://alation-agent-keao.vercel.app/

## Implementation
- **Platform**: OpenAI Agent Builder
- **Model**: gpt-4o-mini
- **Tool**: Code Interpreter
- **Dataset**: `data/cleaned/employee_cleaned.csv`

## System Prompt

The agent uses a detailed system prompt that includes:
- Role definition as HR data analysis agent
- Conversation handling rules
- Data analysis workflow
- Question-specific rules for the three required questions

Full system prompt is available in the agent configuration on OpenAI platform.

## Questions Answered
1. Which Region(s) offer the highest salary to employees on average?
2. Show me a list of top performers in each department?
3. Show me a list of the most tenured employees in each department?

## Recreation Instructions

1. Create a new agent in OpenAI Agent Builder (platform.openai.com)
2. Configure the agent with:
   - Model: gpt-4o-mini
   - Tool: Code Interpreter
   - Upload `data/cleaned/employee_cleaned.csv` to Code Interpreter
3. Set the system prompt (see full prompt in agent configuration)
4. Deploy the agent
