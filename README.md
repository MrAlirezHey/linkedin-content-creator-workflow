
# **LinkedIn Content Creator Workflow**

This project demonstrates an automated workflow for creating content for LinkedIn posts. The **LinkedIn Content Creator Workflow** integrates several AI-powered tools to help content creators efficiently generate engaging posts based on web search results and topic ideas.

The workflow is designed using **n8n**, a powerful automation tool, to streamline the process of generating and publishing professional content. It pulls relevant information from various sources, synthesizes it, and outputs a cohesive LinkedIn post ready for publishing.

---

## **Workflow Overview**

### **1. Manual Trigger**
- The workflow begins when the user clicks the **"Execute workflow"** button, initiating the process.

### **2. AI Agent (Topic Generation)**
- An AI-powered agent is used to generate a topic suggestion for the LinkedIn post. The agent outputs a specific topic that can be used for web search and content generation.

### **3. Web Search**
- The system sends a **POST request** to the Tavily API, searching the web for content related to the AI-generated topic. This step gathers relevant articles or data that can be used to create the LinkedIn post.

### **4. OpenAI Chat Model for Content Creation**
- The articles retrieved in the previous step are processed by **OpenAI's GPT** model. It synthesizes insights from the articles and creates a professional LinkedIn post that:
  - Contains a compelling introduction.
  - Integrates insights from multiple articles into a cohesive narrative.
  - Ends with an inspiring conclusion and call to action.

### **5. Final AI Agent (Content Synthesis and Post Creation)**
- After generating the post, the AI agent refines and finalizes the content to ensure it is concise, professional, and optimized for LinkedIn. This includes adding relevant hashtags and emojis to enhance engagement.

### **6. Scheduling (Optional)**
- The workflow can be scheduled to run at regular intervals (e.g., daily at 7 AM), ensuring that fresh content is generated and ready to be posted.

---

## **Features**

- **Automated Content Generation**: Automatically generates relevant and professional LinkedIn posts by pulling data from the web.
- **AI-Powered Topic Suggestion**: Uses AI to suggest a relevant topic based on current trends or specified keywords.
- **Web Search Integration**: Uses the **Tavily API** to perform web searches for content creation.
- **Post Synthesis with OpenAI**: Integrates **OpenAI's GPT model** to synthesize content from multiple sources into a cohesive LinkedIn post.
- **Customizable Scheduling**: The workflow can be scheduled to run at specific times to automate content creation regularly.

---

## **Tech Stack**

- **n8n**: An automation tool for building workflows and connecting multiple services.
- **OpenAI GPT-4**: Used for natural language processing and content creation.
- **Tavily API**: Used to perform web searches and retrieve relevant articles for content generation.
- **Node.js**: Used for the execution of the n8n automation workflow.
- **Docker**: Optionally used for deploying the n8n workflow in isolated environments.

---

## **Setup Instructions**

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/linkedin-content-creator-workflow.git
cd linkedin-content-creator-workflow
```

### 2. Install Dependencies

Ensure that you have **n8n** installed and configured. You can follow the official installation guide for **n8n** if it's not already installed.

```bash
npm install -g n8n
```

Alternatively, use **Docker** to set up **n8n**:

```bash
docker run --name n8n -d -p 5678:5678 n8nio/n8n
```

### 3. Configure Environment Variables

Create a `.env` file in the root of the project with the following variables:

```env
TAVILY_API_KEY=your_tavily_api_key_here
OPENAI_API_KEY=your_openai_api_key_here
```

### 4. Import Workflow into n8n

- Navigate to your **n8n dashboard** at `http://localhost:5678` (if running locally).
- Import the workflow **Linkedin Content Creator Workflow** (`Linkedin Content Creator Workflow.json`) into n8n.
- Configure the necessary API keys and test the workflow to ensure it’s working properly.

### 5. Run the Workflow

You can manually execute the workflow by clicking the **"Execute workflow"** button. Optionally, you can schedule the workflow to run periodically.

---

## **Usage**

Once the workflow is set up:

1. **Trigger the Workflow**: You can either manually trigger it by clicking the "Execute workflow" button or set it to run on a schedule.
2. **Web Search**: The workflow automatically searches the web for relevant content based on an AI-generated topic.
3. **Content Creation**: The OpenAI model generates a LinkedIn post by synthesizing the content retrieved from the web.
4. **Post Generation**: The AI ensures the content is concise, inspiring, and professional, ready for publication.

---

## **License**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## **Acknowledgments**

- **n8n**: For providing the automation platform to connect all services.
- **OpenAI GPT**: For providing the AI-powered content generation.
- **Tavily**: For the web search API.
  
---
