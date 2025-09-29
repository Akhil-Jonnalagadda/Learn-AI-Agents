
---

# **Day 2 – Components of an AI Agent**

---

## **1. Introduction**

In Day 1, we learned what an AI Agent is and saw how it follows the cycle **Sense → Think → Act → (Learn)**.
But how does an agent actually do all of this?

Just like a car has different parts (engine, wheels, brakes), an **AI Agent** also has different components that allow it to function.
The main components are:

1. **Sensors** – to perceive input
2. **Decision-making (Brain)** – to think
3. **Actuators** – to act
4. **Memory** – to remember and learn

---

## **2. Sensors – How Agents Perceive the World**

Sensors are the way an agent collects information from its environment.

* For a **robot**, sensors can be cameras, microphones, GPS, or LiDAR.
* For a **chatbot**, the sensor is your text input.
* For **Google Maps**, sensors are GPS data, traffic signals, and location updates.

👉 Example: A self-driving car’s camera sees a red light. That’s sensing.

---

## **3. Decision-Making – The Brain of the Agent**

After sensing, the agent needs to **decide** what to do. This is like the **brain**.

* In a simple system, decisions are just **rules** (if light = red → stop).
* In complex systems, decisions are made using **machine learning** or **reinforcement learning**.

👉 Example: A chatbot reads your message: *“What’s the weather?”*.
The brain decides: *“Fetch weather data and reply.”*

---

## **4. Actuators – How Agents Take Action**

Actuators are the parts that let the agent perform actions in the environment.

* In a **robot**, actuators are motors, wheels, and arms.
* In a **chatbot**, actuators are the text messages it sends back.
* In **Google Maps**, actuators are the arrows and voice instructions it gives you.

👉 Example: A self-driving car applies brakes after seeing a red light. That’s acting.

---

## **5. Memory – Learning from the Past**

Not all agents have memory, but advanced ones do.
Memory helps an agent improve and make better decisions over time.

* **Robot vacuum cleaner** remembers the map of your room.
* **Netflix** remembers your watch history to give better suggestions.
* **ChatGPT** remembers context during a conversation (short-term memory).

👉 Example: If a pizza delivery agent always gets stuck in traffic on Route A, it will learn to avoid it next time.

---

## **6. Bringing It All Together**

Let’s combine these components with a simple story:

Imagine an **AI personal assistant agent** on your phone.

* **Sensors:** It listens to your voice.
* **Decision-making:** It understands you said *“Set an alarm for 7 AM.”*
* **Actuator:** It sets the alarm in your clock app.
* **Memory:** It remembers you usually wake up at 7, so next time it suggests an alarm automatically.

---

## **7. Java Example – Agent with Components**

Let’s simulate an agent that senses if it’s **day** or **night**, decides what to do, acts, and also uses memory to count how many times it has worked or slept.

```java
import java.util.Random;

class SimpleAgentWithMemory {
    private int workCount = 0;
    private int sleepCount = 0;
    private Random random = new Random();

    // Sensor: Perceive environment (day or night)
    public String sense() {
        String[] time = {"day", "night"};
        return time[random.nextInt(time.length)];
    }

    // Brain: Decide action
    public String decide(String situation) {
        if (situation.equals("day")) {
            return "work";
        } else {
            return "sleep";
        }
    }

    // Actuator: Perform action
    public void act(String action) {
        if (action.equals("work")) {
            workCount++;
            System.out.println("Agent works 💻 (Total worked: " + workCount + ")");
        } else {
            sleepCount++;
            System.out.println("Agent sleeps 😴 (Total slept: " + sleepCount + ")");
        }
    }
}

public class AgentComponentDemo {
    public static void main(String[] args) {
        SimpleAgentWithMemory agent = new SimpleAgentWithMemory();

        for (int i = 1; i <= 5; i++) {
            System.out.println("\nStep " + i);
            String situation = agent.sense(); // Sensor
            System.out.println("Environment: " + situation);

            String decision = agent.decide(situation); // Brain
            System.out.println("Agent decides to: " + decision);

            agent.act(decision); // Actuator
        }
    }
}
```

### ✅ Example Output

```
Step 1
Environment: day
Agent decides to: work
Agent works 💻 (Total worked: 1)

Step 2
Environment: night
Agent decides to: sleep
Agent sleeps 😴 (Total slept: 1)
```

---

## **8. Summary (Day 2)**

* Every AI Agent is made of **Sensors, Brain, Actuators, and Memory**.
* **Sensors** collect information (input).
* **Brain** decides the action.
* **Actuators** perform the action.
* **Memory** helps improve decisions over time.
* Real-world examples:

  * Self-driving cars (cameras → decision → brakes).
  * Chatbots (text input → decision → text reply).
  * Netflix (watch history → decision → recommendation).
* We built a simple **Java agent with memory** that works during the day and sleeps at night.

---

