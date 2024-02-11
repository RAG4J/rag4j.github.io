---
layout: page
title: Examples
permalink: /examples/
---
Both projects contain examples. For java the examples are in the `src/main/java/org/rag/applications` folder. For Python are in the root folder of the project `rag4p`. For both projects we used interfaces as much as possible to reflect the main components. In the design it is important that you do not have to initialise the whole project to start working with one of the components. Below is an example that works with an LLM to answer q question. You do not have to initialise the Retriever to execute the flow.

**Java code sample**
```java
KeyLoader keyLoader = new KeyLoader();
AnswerGenerator answerGenerator = new OpenAIAnswerGenerator(keyLoader);

String question = "Since when was the Vasa available for the public to visit?";
String context = "By Friday 16 February 1962, the ship is ready to be displayed to the general public at the " +
        "newly-constructed Wasa Shipyard, where visitors can see Vasa while a team of conservators, " +
        "carpenters and other technicians work to preserve the ship.";

String answer = answerGenerator.generateAnswer(question, context);
System.out.printf("The question is: %s%n", question);
System.out.printf("The answer is: %s%n", answer);
```

**Python code sample**
```python
from dotenv import load_dotenv
load_dotenv()

key_loader = KeyLoader()

question = "Since when was the Vasa available for the public to visit?"
context = ("By Friday 16 February 1962, the ship is ready to be displayed to the general public at the "
           "newly-constructed Wasa Shipyard, where visitors can see Vasa while a team of conservators, "
           "carpenters and other technicians work to preserve the ship.")

answer_generator = OpenaiAnswerGenerator(openai_api_key=key_loader.get_openai_api_key())
answer = answer_generator.generate_answer(question, context)

print(f"Question: {question}")
print(f"Answer: {answer}")
```
