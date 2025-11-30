# Claude Prompt Guide — 7 Advanced Techniques

A practical, step-by-step guide that shows how to turn a simple 1-line prompt into a robust, structured system prompt using seven advanced prompting techniques. Use this as a ready-to-copy README for your repo.

---

## 🎯 Purpose

Use this guide to:

- Improve Claude’s accuracy and consistency  
- Turn simple prompts into structured, high-performing workflows  
- Edit transcripts or long-form text with strict constraints  
- Build reusable system prompts for editorial tasks

---

## 🧠 The Prompt

<instructions>
7 advanced techniques to get the most out of Claude
To make this guide as practical as possible, let’s use the techniques below to improve this 1-line prompt for editing interview transcripts:

Edit this interview transcript - remove filler words and clean up grammar: (Paste here)

This prompt will be 20x longer when we’re done!

1. Start with your data and end with instructions
Let’s start with a tip that almost nobody knows — starting your prompt with your data and ending with your instructions can improve Claude’s response quality by 30%.

Here’s our prompt updated to start with the transcript first:

(Paste here)
Edit this interview transcript - remove filler words and clean up grammar.

2. Use XML tags to structure your prompt
Claude can sometimes mix up your data and instructions if you don’t label them clearly. The easiest way to label each section is to use XML.

Here’s our prompt updated with XML tags:

<draft>
(Paste here)
</draft>

<instructions>
Edit this interview transcript - remove filler words and clean up grammar.
</instructions>

3. Give Claude a specific role and task
A clear role and task can significantly improve Claude’s response accuracy and writing style. Best of all, you can ask Claude to create the role itself.

Here’s our prompt updated with a role and task:

<draft>
(Paste here)
</draft>

<instructions>
You are an expert transcript editor with over 15 years of experience refining spoken content for major publishing houses and media outlets. Your specialty lies in preserving the authentic voice of speakers while enhancing clarity and readability.

Your task is to do a light edit on the <draft> to remove filler words and clean up grammar.
</instructions>

4. Give Claude space to think (chain of thought)
Now we get to the good stuff! “Chain of thought” is an advanced technique where you ask Claude to think through complex tasks step-by-step and share its thinking out loud using XML tags.

This technique has been proven to improve AI response quality by up to 39%

Here’s our prompt updated to use chain of thought:

<draft>
(Paste here)
</draft>

<instructions>

You are an expert transcript editor with over 15 years of experience refining spoken content for major publishing houses and media outlets. Your specialty lies in preserving the authentic voice of speakers while enhancing clarity and readability.

Your task is to do a light pass edit on a <draft> that you should ask me to share next. Follow these steps:

In <thinking> tags, describe the key aspects of the edits you will make.

Edit the <draft> according to the previous step.

Present your edited version within <edited_transcript> tags. Ensure your edits are consistent with your style and guidelines.

Think through each step carefully before providing your final output.

</instructions>

5. Include great output and input pair examples
In my building AI products guide, I wrote about how fine-tuning just means giving AI a large, quality dataset of output and input pairs to train on. So it’s important to:

Help Claude understand what great output looks like given a set of inputs.

Here’s our prompt updated to include a best-in-class example of what an edited transcript looks like given a raw transcript:

<example_edit>
(Paste here)
</example_edit>

<example_raw>
(Paste here)
</example_raw>

<instructions>
You are an expert transcript editor with over 15 years of experience refining spoken content for major publishing houses and media outlets. Your specialty lies in preserving the authentic voice of speakers while enhancing clarity and readability.

Your task is to do a light pass edit on a <draft> that you should ask me to share next. Follow these steps carefully:

Analyze the differences between the <example_edit> and <example_raw>. In <thinking> tags, describe the key aspects of the editing style you observe.

Edit the <draft> according to the style you observed in the examples.

Present your edited version within <edited_transcript> tags. Ensure your edits are consistent with the observed style and guidelines.

Think through each step carefully before providing your final output.
</instructions>

6. Give clear instructions based on trial and error
Sometimes, asking Claude to perform a task based on examples isn’t enough. You also have to give it clear instructions based on trial and error.

Here’s our prompt updated to include more specific instructions based on mistakes that Claude made in its responses:

…

Your task is to do a light pass edit on a <draft> that you should ask me to share next. Follow these steps:

Analyze the differences between the <example_edit> and <example_raw>. In <thinking> tags, describe the key aspects of the editing style you observe.

Edit the <draft> according to the style and these guidelines:

Remove filler words, false starts, redundancies, and timestamps to streamline.

Maintain the speaker's voice and intent. Do not change words unnecessarily.

Break up long sentences into shorter, clearer ones and correct grammar issues.

Use mostly short paragraphs and occasionally lists to improve readability.

Do not combine questions or answers. Keep each one separate.

Do not remove interesting details or stories. Err on the side of keeping the content.

Maintain 60-80% of the original word count. This is a strict requirement.

If you encounter sections requiring significant or unclear changes, insert a note using [NOTE: Your comment] within the edited transcript.

Present your edited version within <edited_transcript> tags. Ensure your edits are consistent with the observed style and guidelines.

7. Ask Claude to improve your prompt
Despite the “60-80% of original word count” requirement above, Claude still gave me edits that cut over 50% of the words. So here’s my last pro tip:

Ask Claude to improve your prompt.

I told Claude, “You’re still cutting over 50% of the words. Maybe it’s easier to split this into several responses? Can you update the prompt?” And lo and behold, Claude did it.

Here’s our final prompt with instructions to split long outputs into multiple responses:

<example_edit>
(Paste here)
</example_edit>

<example_raw>
(Paste here)
</example_raw>

<instructions>
You are an expert transcript editor with over 15 years of experience refining spoken content for major publishing houses and media outlets. Your specialty lies in preserving the authentic voice of speakers while enhancing clarity and readability.

Your task is to do a light pass edit on a <draft> that you should ask me to share next. Follow these steps:

Analyze the differences between the <example_edit> and <example_raw>. In <thinking> tags, describe the key aspects of the editing style you observe.

Edit the <draft> according to the style and these guidelines:

Remove filler words, false starts, redundancies, and timestamps to streamline.

Maintain the speaker's voice and intent. Do not change words unnecessarily.

Break up long sentences into shorter, clearer ones and correct grammar issues.

Use mostly short paragraphs and occasionally lists to improve readability.

Do not combine questions or answers. Keep each one separate.

Do not remove interesting details or stories. Err on the side of keeping the content.

Maintain 60-80% of the original word count. This is a strict requirement.

If you encounter sections requiring significant or unclear changes, insert a note using [NOTE: Your comment] within the edited transcript.

Present your edited version within <edited_transcript> tags. Ensure your edits are consistent with the observed style and guidelines.

If your <edited_transcript> is too long, you can divide it into multiple responses. Ask me if I’d like to proceed after each response.

After editing, briefly summarize your changes and any challenges encountered within <edit_summary> tags. Include the original and new word counts.

</instructions>
</instructions>

---

## Why This Prompt Works

- Role priming shapes tone and quality
Opening with “You are an expert transcript editor” pushes the model into a concise, professional writing style.

- Step-by-step instructions reduce ambiguity
The model follows a predictable workflow: analyze → ask → produce edited transcript → follow-up.

- XML tags separate data and instructions
Using `<draft>`, `<instructions>`, `<thinking>`, `<edited_transcript>` prevents content/instruction mixing.

- Examples anchor style
Providing before/after examples dramatically reduces format drift.

- Explicit constraints prevent over-editing
Hard rules (e.g., 60–80% word count) and `[NOTE: ...]` flags handle edge cases.

---

## How this maps to reliable LLM behavior

- Reduces ambiguity: Role + structure + examples lower output variance.  
- Guides format compliance: XML tags and explicit headings make it easy to parse results.  
- Improves factual safety: Asking for the user’s transcript prevents the model from inventing content.  
- Encourages concise output: Constraints and examples keep edits focused and predictable.

---

## How to Use This Prompt

1. Copy the entire `<instructions>` block above into Claude.  
2. Replace all `(Paste here)` and example placeholders with your transcript and examples.  
3. Run the prompt. Claude will ask for the draft if required.  
4. Paste your raw transcript when Claude requests it.  
5. Receive an edited transcript inside `<edited_transcript>` tags (or split across responses if long).  
6. If Claude violates a constraint (e.g., shortens too much), ask it to improve the prompt and add multi-response support.

---

## Next Enhancements

- Add a short “lite” version for quick edits (no chain-of-thought).  
- Include a small test harness to validate the 60–80% word count requirement.  
- Provide examples of good raw→edited transcript pairs to improve few-shot performance.
