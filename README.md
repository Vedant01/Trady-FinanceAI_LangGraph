
## **Project Overview**
The project aims to build an intelligent finance assistant capable of answering complex queries about financial metrics. This assistant leverages advanced AI techniques and integrates various tools to provide accurate financial information based on user queries, including real-time stock data.

---

## **Components and Technologies Used**

### **Language Model Integration**
- **Model**: Llama 3.1 (or a similar large language model).
- **Library**: `langchain_groq` for interfacing with the language model.
- **Purpose**: 
  - Process natural language queries.
  - Generate appropriate responses.
  - Interact with tools to fetch and compute required data.

---

### **Tool Integration**
A set of tools provided by the `langchain_core` library includes:
- **company_address**: Fetches the address of a company based on its stock ticker.
- **fulltime_employees**: Retrieves the number of full-time employees for a given company.
- **last_close_price**: Provides the last closing price of a company's stock.
- **EBITDA**: Returns the EBITDA (Earnings Before Interest, Taxes, Depreciation, and Amortization) for a company.
- **total_debt**: Retrieves the total debt of a company.
- **total_revenue**: Provides the total revenue of a company.
- **debt_to_equity_ratio**: Calculates the debt-to-equity ratio of a company.
- **get_real_time_price**: Fetches the real-time price of a specified stock ticker using the Alpaca API.

---

### **State Management and Execution**
- **State Graph**: Manages the flow of execution between the language model and tools using `StateGraph` from the `langgraph` library.
- **Graph Logic**:
  - **Nodes**: Define actions such as calling the language model (`llama3`) or executing tools (`action`).
  - **Conditional Edges**: Determine whether to continue interacting with the model or executing actions based on the presence of tool calls.
  - **Graph Execution**: Utilizes methods to run the state graph, invoking tools and processing results.

---

### **Custom Agent**
- **Agent Class**: `ReActAgent`, which integrates the language model and tools to facilitate interactions through the state graph.
- **Functionality**:
  - Handles user queries.
  - Determines if and which tools to call based on the query.
  - Manages tool executions and combines results with model responses.

---

### **User Interaction**
- **Interface**: Users interact with the system by sending queries such as:
  - “Compare total revenue of Amazon and Google.”
  - “What is the real-time price of AAPL?”
- **Response Handling**:
  - The system fetches relevant data using the integrated tools.
  - Provides comprehensive and accurate responses.

---

### **Visualization**
- **Graph Visualization**: Uses libraries like `graphviz` to visualize the state graph, aiding in understanding the flow and interactions.

---

## **Key Technologies**
- **Programming Language**: Python.
- **Libraries and Tools**:
  - `langchain_groq`: For integrating and managing the language model.
  - `langchain_core`: For tool definitions and message handling.
  - `langgraph`: For defining and managing the state graph.
  - `yfinance`: For fetching historical financial data.
  - `alpaca-trade-api`: For real-time stock price extraction.
  - `graphviz`: For visualizing the state graph.

---

## **Example Queries**
1. “Compare total revenue of Amazon and Google.”
2. “What is the real-time price of AAPL?”
3. “What is the debt-to-equity ratio for Tesla?”

By combining advanced AI with real-time financial tools, this project demonstrates a robust and scalable intelligent finance assistant.
