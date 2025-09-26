## Design and Implementation of LangChain Expression Language (LCEL) Expressions

### AIM:
To design and implement a LangChain Expression Language (LCEL) expression that utilizes at least two prompt parameters and three key components (prompt, model, and output parser), and to evaluate its functionality by analyzing relevant examples of its application in real-world scenarios.

### PROBLEM STATEMENT:
Natural Language Processing (NLP) applications often require chaining multiple components such as prompts, models, and parsers to process user queries effectively. LangChain Expression Language (LCEL) provides a declarative way to define such chains, making them reusable and composable. The problem is to build an LCEL expression that:
1.Accepts at least two prompt parameters.
2.Uses three core components (prompt, model, output parser).
3.Demonstrates how LCEL can be applied in real-world scenarios like summarization or Q&A.

### DESIGN STEPS:

### STEP 1: Define a structured PromptTemplate with placeholders for at least two parameters.
### STEP 2: Select a Language Model (e.g., OpenAI’s GPT or other supported models).
### STEP 3: Add an Output Parser to format/validate the model’s response.
### STEP 4: Chain all components using LCEL syntax.
### STEP 5: Test the LCEL expression with real input values.

### PROGRAM:
```
from langchain.prompts import ChatPromptTemplate
from langchain.chat_models import ChatOpenAI
from langchain.schema import StrOutputParser  

prompt = ChatPromptTemplate.from_template(
    "You are a helpful assistant. Summarize the text in {style} style. "
    "Here is the text: {text}"
)

model = ChatOpenAI(model_name="gpt-3.5-turbo", temperature=0)

parser = StrOutputParser()

chain = prompt | model | parser

output = chain.invoke({
    "style": "bullet points",
    "text": "LangChain is a framework that simplifies the development of applications "
            "powered by large language models by providing tools for chaining components."
})

print("Generated Output:\n", output)
```
### OUTPUT:

<img width="1142" height="107" alt="image" src="https://github.com/user-attachments/assets/75f88557-623d-4c66-88c6-9a11176bdc51" />

### RESULT:

Thus, the LangChain Expression Language (LCEL) expression that utilizes two prompt parameters and three key components (prompt, model, and output parser) was designed and implemented successfully. And also evaluated its functionality by analyzing relevant examples of its application in real-world scenarios.
