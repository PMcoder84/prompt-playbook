# Draft PRD Generator Prompt

A structured prompt that converts rough product notes into a well-written, concise PRD following a clear, repeatable template.  
This is designed for Product Managers who want to quickly transform messy notes into a polished PRD without losing clarity or structure.

---

## 🎯 Purpose  
Use this prompt when you have:
- Raw notes from customer calls, brainstorming, meetings, or problem statements  
- A need to quickly produce a structured, two-page Product Requirements Document  
- A desire to enforce consistency across PRDs in your team or portfolio

This prompt provides a clear workflow:
1. Learn your preferred PRD style  
2. Ask you for your notes  
3. Convert those notes into a structured, milestone-driven PRD  
4. Present the output inside clean tags for copy/paste or iteration  

---

## 🧠 The Prompt

<instructions>
You are a senior product leader and a clear written communicator. Your task is to transform my rough notes into a great PRD. 

Please follow these steps carefully:
1. Analyze the <reference> to understand my desired style and format. In <thinking> tags, briefly summarize the key characteristics of my PRD template.
2. Ask me to share my notes next. 
3. Structure the PRD as follows:
- Problem: Clearly describe in a few short sentences: Who is the customer? What is the customer's problem? How do we know that this is a problem?
- Goals: Include 1 goal metric and 2-3 input metrics that drive the goal. 
- Solution: Clearly describe the solution and milestones. For each milestone, write concise user stories in first person view ("I see...", "I can...") with nested bullet points describing how the feature will work.
- Meeting notes: Make this section, but leave it blank for now.
- Other bonus sections include the launch plan and experiment plan.
- Limit the PRD to 2 pages max.
4. Present your response using:
<draft_prd> tags for the structured document
<follow_up> tags for follow-up items

If you need more information, please ask me. Be as clear, concise, and specific as possible. 
</instructions>

<reference>
Problem
Describe the problem that you’re trying to solve in a few sentences. Answer these questions:
Who is the customer?
What is the customer problem?
How do we know that this is a problem?  (e.g., link to customer research and data)

Example: Topic selector during Pinterest new user onboarding

New users want to view topics that they're interested in when they first sign up for Pinterest. 

Today, all new users see the same feed of the most popular content. This content is dominated by a few categories like women's fashion and decor that don't align with the diverse interests of all new users (see appendix for research). 

We want to test letting new users select topics during onboarding to personalize their feed.
Goals
List one output goal and 2-3 input metrics that’ll drive the goal. (Optional) List non-goals that you do not plan to address with this feature.

Example: 

Output: Grow activation rate by 20% (% of sign ups who visit again in 7 days)

Inputs: 
- users who visit topic selector screen
- who select a topic, # of topics selected
- who pin during their first session

Requirements

Describe what the solution is at a high level first. If there are multiple milestones, list them clearly. 

For each milestone:
Write each feature as a user story and try to be as concise as possible. 
Mark clearly which features are P0 and P1.
Highlight any open questions for discussion async.

Include a wireframe or a draft design to bring important features to life.

Example: 

We want to test this topic selector in two milestones:

M1: Test topic selector in onboarding and personalize feed based on topics
M2: Test using age, gender, and language signals to personalize the topic selector

M1: Test topic selector in onboarding flow and personalized feed based on topics
Link to design

Example:

P0
See topic selector during onboarding

As a new user, when I am signing up to Pinterest,
then I see a "Pick 5 or more topics to personalize your feed" screen
after signing up with my email or phone number.

On this screen, I see a grid of the most popular topics and a button labeled “Meet your home feed” that is initially disabled. When I select 5 or more topics, the button activates and I can click on it to visit my Home Feed.

Discussion:
Peter: How should we rank the topics?
P0
Home feed with content from topics that I selected

When I visit the home feed for the first time,
I see popular and recent content from the topics that I’ve selected.

M2: Test using age, gender, and language signals to personalize the topic selector...

TBD

Meeting notes

Take meeting notes in a dedicated section directly in the PRD. This ensures that the latest discussions and decisions are captured in a single document.

Example:

Team sync - 5/10

Peter: Why are we forcing users to select 5+ topics?
Wendy: Data science has research showing that users who select at least 5 topics tend to retain better. Bob: Suggest A/B the minimum number of topics in a subsequent experiment.

Launch plan

Define your launch plan whether it’s a staged rollout or an experiment. For experiments, define the success criteria, eligibility, test, control, and ramp plan.

Example: Staged rollout

Target date
Milestone
Description
Notes
YY-MM-DD
Alpha
Internal team testing
On track
YY-MM-DD
Beta
First 100 customers
On track
YY-MM-DD
Launch
General availability
On track

Example: 

Topic selector experiment
Success criteria: Grow activation rate by 20% (% of sign ups who visit again in 7 days)
Eligibility: People who sign up for Pinterest on web and mweb.
Test: Experience described above.
Control: Existing onboarding experience without “topic selector” screen.
Ramp plan: 50/50 experiment.

Appendix

Include relevant info like customer interviews, competitive research, supporting data, and more. Keep the main spec short but the appendix can be as long as you want.
</reference>

---

## Why This Prompt Works

- Role priming shapes tone and quality
Opening with “You are a senior product leader” pushes the model into a concise, strategic writing style.

- Step-by-step instructions reduce ambiguity
The model follows a predictable workflow: analyze → ask → produce PRD → follow-up.

- Explicit format requirements
Specifying Problem, Goals, Milestones, User Stories, Launch Plan, and Meeting Notes ensures complete coverage with no missing sections.

- Use of custom tags
<thinking>, <draft_prd>, and <follow_up> tags force the LLM to separate reasoning, final output, and next actions — improving readability and structure.

- Reference-driven style alignment
Providing a real PRD example helps the model mirror tone, length, clarity, and structure.

- User stories in first-person POV
“I see…”, “I can…” generates more intuitive and user-centered requirements.

- Page limit constraint
Forces the model to keep the PRD concise and business-ready without drifting into long essays.

- Human-in-the-loop trigger
Step 2 ensures the model never invents product details and always requests the user's notes first.

---
## How this maps to reliable LLM behavior

Reduces ambiguity: Role + concrete structure + examples lower variance of answers.

Guides format compliance: Tags and explicit section headings make it easier to parse or convert to markdown/HTML later.

Improves factual safety: The instruction to ask for the user’s notes prevents the model from inventing product specifics.

Encourages concise output: The two-page limit and explicit bullets help keep the PRD resume/portfolio-friendly.

---

## How to Use This Prompt

1. Paste the entire prompt into your LLM.

2. Replace the <reference> section with your preferred PRD example (or leave as-is).

3. The model will summarize the style and ask for your notes.

4. Paste your rough notes.

5. Receive a clean PRD inside <draft_prd> tags.

---

## Next Enhancements

- Specify output format (e.g., Markdown) so it’s copy-paste ready: Output: markdown, headings H2/H3.

- Clarify two-page limit as word count (e.g., “~400–600 words” or “max 800 words”) so model enforces length precisely.

- State audience/readers (Engineering? Execs?) to tune tone and detail level.

- Define priority labels if you have a custom scheme (P0/P1 meaning).