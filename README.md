# EXP-04: Advanced Prompt Engineering Techniques


---

# AIM

To implement and understand advanced prompt engineering techniques such as **Zero-shot Prompting, Few-shot Prompting, Chain of Thought, Persona Pattern, Reverse Prompting, Graph Prompting, and Active Prompting** using an engineering case study.

The generated AI responses are evaluated based on **reasoning, correctness, and token usage**.

---

# ENGINEERING CASE STUDY

**Application:** AI-Powered Smart Irrigation System

A Smart Irrigation System uses sensors, IoT devices, and AI to determine when crops require watering. The system can analyze parameters such as **soil moisture, temperature, humidity, and weather conditions** to make irrigation decisions.

---

# AI PLATFORMS

The prompts can be tested using:

* ChatGPT
* Google Gemini
* Claude AI

---

# ALGORITHM

### Step 1

Select an engineering application.

**Application:** Smart Irrigation System

### Step 2

Select AI platforms for testing.

* ChatGPT
* Google Gemini
* Claude AI

### Step 3

Apply the seven advanced prompting techniques.

1. Zero-shot Prompting
2. Few-shot Prompting
3. Chain of Thought
4. Persona Pattern
5. Reverse Prompting
6. Graph Prompting
7. Active Prompting

### Step 4

Generate responses from the AI platforms.

### Step 5

Compare the responses.

### Step 6

Evaluate the outputs based on:

* Reasoning
* Correctness
* Token Usage

---

# 1. ZERO-SHOT PROMPTING

## Description

Zero-shot prompting asks the AI to perform a task **without providing examples**. The AI must understand the task using only the given instruction.

### Example Prompt

> Determine whether irrigation is required when soil moisture is 25%, temperature is 32°C, and humidity is 40%.

### Sample Output

**AI:**
Irrigation is likely required because the soil moisture is relatively low, while the temperature is high and humidity is moderate. Watering the crop can help maintain adequate soil moisture.

### Evaluation

* Simple and direct.
* Requires no examples.
* Quick response.
* Uses less prompt information.
* Reasoning may be less detailed.

---

# 2. FEW-SHOT PROMPTING

## Description

Few-shot prompting provides the AI with a few examples before asking it to perform a similar task. The examples help the AI understand the expected pattern.

### Example Prompt

> Determine whether irrigation is required based on soil moisture.
>
> **Example 1:** Soil moisture = 80% → Irrigation = No
> **Example 2:** Soil moisture = 60% → Irrigation = No
> **Example 3:** Soil moisture = 25% → Irrigation = Yes
>
> **Question:** Soil moisture = 30%. Should irrigation be turned ON or OFF?

### Sample Output

**AI:**
**Irrigation: ON**

The soil moisture is low and is closer to the example where irrigation was required.

### Evaluation

* Uses examples to guide the AI.
* Produces more consistent responses.
* Useful for classification tasks.
* Requires more input tokens because examples are included.
* Accuracy depends on the quality of examples.

---

# 3. CHAIN OF THOUGHT PROMPTING

## Description

Chain of Thought Prompting encourages the AI to solve a problem through a sequence of logical reasoning steps before giving the final answer.

### Example Prompt

> Analyze the following Smart Irrigation situation step-by-step: Soil moisture is 20%, temperature is 35°C, humidity is 30%, and no rain is expected. Determine whether irrigation should be activated.

### Sample Output

**AI:**

1. Soil moisture is 20%, indicating relatively dry soil.
2. Temperature is 35°C, which increases water loss.
3. Humidity is only 30%, increasing evaporation.
4. No rainfall is expected.
5. Therefore, irrigation should be activated to provide water to the crops.

**Final Decision:** Irrigation ON.

### Evaluation

* Provides logical reasoning.
* Makes the decision easier to understand.
* Useful for engineering decision-making.
* Requires more tokens than a simple answer.
* Detailed reasoning may not always be necessary for simple tasks.

---

# 4. PERSONA PATTERN

## Description

Persona Pattern assigns a specific professional role to the AI. The AI then responds from the perspective of that role.

### Example Prompt

> Act as an IoT and agricultural automation engineer. Design a Smart Irrigation decision system using soil moisture, temperature, humidity, and rainfall information. Explain the system in simple technical language.

### Sample Output

**AI:**

As an IoT and agricultural automation engineer, I recommend the following system:

1. Install soil-moisture sensors in the agricultural field.
2. Measure temperature and humidity using environmental sensors.
3. Obtain rainfall information from a weather service.
4. Send sensor readings to a microcontroller or IoT platform.
5. Analyze the collected values using predefined rules or an AI model.
6. Activate the water pump when irrigation is required.
7. Stop irrigation when sufficient soil moisture is detected.

### Evaluation

* Produces domain-specific information.
* Provides a professional engineering perspective.
* Improves relevance.
* Useful for technical project development.
* The quality depends on the selected persona.

---

# 5. REVERSE PROMPTING

## Description

Reverse Prompting asks the AI to **generate or improve the prompt itself** based on a desired task or output.

Instead of directly asking for a solution, the user asks the AI to identify what information is needed and create an effective prompt.

### Example Prompt

> I want an AI system to decide when a Smart Irrigation system should turn the water pump ON or OFF. Identify the information required and create an effective prompt that can be used to obtain a reliable irrigation decision.

### Sample Output

**AI:**

The prompt should include:

* Soil moisture percentage
* Temperature
* Humidity
* Rainfall forecast
* Crop type
* Current irrigation status

**Generated Prompt:**

> Act as a Smart Agriculture Engineer. Analyze soil moisture, temperature, humidity, rainfall forecast, and crop type. Determine whether irrigation should be ON or OFF. Provide the decision, important factors, and a short explanation.

### Evaluation

* Helps create better prompts.
* Identifies missing information.
* Useful for prompt optimization.
* Improves the quality of future AI interactions.
* Requires additional interaction to create the final prompt.

---

# 6. GRAPH PROMPTING

## Description

Graph Prompting represents information as **nodes and relationships**. It is useful for engineering systems where different components are connected.

### Example Prompt

> Represent a Smart Irrigation System as a graph. Show the relationship between sensors, controller, AI decision system, water pump, and crops.

### Sample Output

```text
[Soil Moisture Sensor]
          |
          v
[Temperature Sensor] ---> [IoT Controller]
          |                     |
          v                     v
[Humidity Sensor] ------> [AI Decision]
                                |
                         +------+------+
                         |             |
                        ON            OFF
                         |             |
                         v             v
                    [Water Pump]   [Pump OFF]
                         |
                         v
                       [Crops]
```

### Evaluation

* Clearly shows relationships between system components.
* Useful for system design.
* Easy to understand.
* Helps visualize data flow and decision flow.
* More useful for interconnected engineering systems than simple text descriptions.

---

# 7. ACTIVE PROMPTING

## Description

Active Prompting allows the AI to identify uncertain or difficult cases and request additional information or clarification before making a final decision.

### Example Prompt

> Act as a Smart Irrigation assistant. Analyze the given sensor information and identify any missing information that could affect the irrigation decision. Ask for clarification if necessary before making the final decision.
>
> Soil moisture = 40%
> Temperature = 30°C
> Humidity = 55%
> Crop type = Unknown
> Rainfall forecast = Unknown

### Sample Output

**AI:**

Before making the final irrigation decision, I need two additional pieces of information:

1. What type of crop is being grown?
2. Is rainfall expected in the next few hours?

These factors can significantly affect the irrigation requirement.

**Decision:** More information is required.

### Evaluation

* Identifies missing information.
* Avoids making an unsupported decision.
* Useful when sensor information is incomplete.
* Improves reliability.
* Requires additional interaction and tokens.

---

# COMPARISON OF ADVANCED PROMPTING TECHNIQUES

| Technique         | Main Purpose                | Reasoning   | Token Usage | Best Use             |
| ----------------- | --------------------------- | ----------- | ----------- | -------------------- |
| Zero-shot         | Direct task                 | Medium      | Low         | Simple decisions     |
| Few-shot          | Learn from examples         | Medium–High | Medium      | Classification       |
| Chain of Thought  | Step-by-step reasoning      | High        | High        | Complex decisions    |
| Persona Pattern   | Expert perspective          | High        | Medium      | Engineering advice   |
| Reverse Prompting | Create/improve prompts      | High        | Medium      | Prompt optimization  |
| Graph Prompting   | Show relationships          | High        | Medium      | System architecture  |
| Active Prompting  | Request missing information | High        | Medium–High | Uncertain situations |

---

# AI TOOL COMPARISON

| Criteria              | ChatGPT   | Gemini    | Claude AI |
| --------------------- | --------- | --------- | --------- |
| Reasoning             | Excellent | Very Good | Excellent |
| Correctness           | Excellent | Very Good | Excellent |
| Instruction Following | Excellent | Very Good | Excellent |
| Structured Output     | Excellent | Very Good | Excellent |
| Token Efficiency      | Very Good | Very Good | Good      |
| Engineering Relevance | Excellent | Very Good | Excellent |

---

# EVALUATION

## 1. Reasoning

Chain of Thought, Persona, Reverse, Graph, and Active Prompting generally provide more reasoning or structured decision support than a simple Zero-shot prompt.

## 2. Correctness

Few-shot prompting can improve consistency when suitable examples are provided. Active Prompting can also improve correctness by identifying missing information before making a decision.

## 3. Token Usage

Zero-shot prompting generally requires the fewest tokens because it does not include examples or extensive instructions.

Few-shot prompting uses additional tokens because examples are included. Chain of Thought and detailed Persona prompts may also produce longer responses.

---

# OVERALL OBSERVATION

* **Zero-shot Prompting** is simple and efficient for straightforward decisions.
* **Few-shot Prompting** improves consistency by providing examples.
* **Chain of Thought Prompting** is useful for complex engineering decisions requiring multiple factors.
* **Persona Pattern** provides domain-specific and professional responses.
* **Reverse Prompting** helps create better prompts by identifying required information.
* **Graph Prompting** is useful for representing relationships between components of an engineering system.
* **Active Prompting** is useful when information is incomplete or uncertain.
* Among the techniques, **Active Prompting and Chain of Thought** are particularly useful for decision-making applications where reliability is important.

---

# RESULT

Thus, the seven Advanced Prompt Engineering Techniques—**Zero-shot Prompting, Few-shot Prompting, Chain of Thought, Persona Pattern, Reverse Prompting, Graph Prompting, and Active Prompting**—were successfully implemented using a **Smart Irrigation System** case study.

The generated responses were evaluated based on **reasoning, correctness, and token usage**.

---

# CONCLUSION

The experiment demonstrates that different prompting techniques are suitable for different engineering requirements.

* **Zero-shot** → simple and fast.
* **Few-shot** → example-based and consistent.
* **Chain of Thought** → detailed reasoning.
* **Persona Pattern** → expert-level perspective.
* **Reverse Prompting** → improves prompt design.
* **Graph Prompting** → represents system relationships.
* **Active Prompting** → handles incomplete information.

Therefore, selecting the appropriate prompt engineering technique can improve the **reasoning, correctness, efficiency, and usefulness** of AI-powered engineering applications.
