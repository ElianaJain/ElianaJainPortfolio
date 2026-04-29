# Developer Content Style Guide
**Version 1.0 | Author: Eliana Jain**

---

## Purpose

This style guide defines content standards for developer-facing documentation. It is designed to be used as a reference by human writers and AI agents alike. Rules are explicit and actionable. Where tone varies by content type, each section specifies its own register.

---

## Core Principles

These principles apply to all content types without exception.

**Accuracy over completeness.** If you are uncertain, say so. Incomplete but accurate documentation is better than complete but inaccurate documentation.

**Respect the reader's time.** Developers read to accomplish something. Get to the point. Every sentence should earn its place.

**Show, don't describe.** Use examples, code samples, and concrete scenarios. Avoid abstract explanations where a concrete one is possible.

**Distinguish evidence from interpretation.** State what is true. Flag what is inferred. Never present an assumption as a fact.

---

## Universal Grammar Rules

These rules apply to all content types. No exceptions.

**Voice:** Use active voice. The subject performs the action.
* Incorrect: "A `403` error is returned when the token has expired."
* Correct: "The API returns a `403` error when the token expires."

**Tense:** Use present tense for documentation. Use past tense only when describing historical events.
* Incorrect: "The function will accept three parameters."
* Correct: "The function accepts three parameters."

**Person:** Use second person (you/your) for user-facing content. Use first person plural (we/our) sparingly and only in conversational or narrative content.
* Incorrect: "Users can configure this setting in the dashboard."
* Correct: "You can configure this setting in the dashboard."

**Sentence length:** Keep sentences under 25 words. If a sentence exceeds 25 words, split it.

**Paragraph length:** Keep paragraphs to 3 to 4 sentences maximum in documentation. Longer paragraphs are acceptable in blog posts and narrative content.

**Em dashes:** Do not use em dashes. Use a period, comma, or colon instead.
* Incorrect: "The endpoint returns a token — use it in subsequent requests."
* Correct: "The endpoint returns a token. Use it in subsequent requests."

**Oxford comma:** Always use the Oxford comma in lists of three or more items.
* Incorrect: "The API supports JSON, XML and CSV."
* Correct: "The API supports JSON, XML, and CSV."

**Contractions:** Use contractions in tutorials, blog posts, and error messages. Avoid contractions in formal API reference documentation.

**Ampersands:** Do not use ampersands in prose. Write "and" in full.

---

## Banned Words and Phrases

Never use the following words or phrases in any content type. They add length without meaning.

| Banned | Suggested |
|--------|-----------|
| leverage | use |
| utilize | use |
| robust | specific description of what makes it strong |
| seamlessly | remove entirely or describe the specific behavior |
| easy | remove entirely — what is easy for one developer is not easy for another |
| simply | remove entirely |
| just | remove entirely |
| straightforward | remove entirely |
| powerful | specific description of capability |
| best-in-class | remove entirely |
| world-class | remove entirely |
| cutting-edge | remove entirely |
| innovative | remove entirely |
| synergy | remove entirely |
| please note | note or remove entirely |
| it should be noted | remove entirely |
| in order to | to |
| due to the fact that | because |
| at this point in time | now |
| a number of | several or a specific number |

---

## UI Element Conventions

Follow Microsoft Writing Style Guide conventions for UI elements.

**Bold** all UI element names when referenced in documentation.
* Incorrect: "Select Save to confirm your changes."
* Correct: "Select **Save** to confirm your changes."

Capitalize UI element names exactly as they appear in the interface. Do not alter capitalization.

**Quotations:** Use quotation marks to call out UI text. Periods must be outside quotation marks.
* Incorrect: Select "Menu."
* Correct: Select "Menu".

Use the following verbs consistently for UI interactions:

| Action | Verb to use |
|--------|-------------|
| Clicking a button | Select |
| Choosing from a menu | Select |
| Entering text | Enter |
| Turning on a toggle | Turn on |
| Turning off a toggle | Turn off |
| Opening a dropdown | Open |
| Checking a checkbox | Select |
| Unchecking a checkbox | Clear |

---

## Code Conventions

Always use code formatting for the following:
- Code samples
- Command-line instructions
- File paths
- Parameter names
- Variable names
- API endpoints
- HTTP methods
- Error codes

Use fenced code blocks with language identifiers.

```python
# Correct: language identifier included
def get_token():
    return token
```

Always include a comment explaining what the code does when the purpose is not immediately obvious.

Always show complete, runnable examples where possible. Avoid partial snippets that require the reader to infer missing context.

For command-line instructions, show the full command including any required flags.

---

## Content Type 1: Tutorials and Getting Started Guides

### Tone

Conversational, encouraging, and precise. A tutorial is a guided experience. Write as if you are sitting next to the reader walking them through the task. Be warm but efficient. Do not be condescending.

### Structure

Every tutorial must follow this structure:

1. **Overview** — What the reader will accomplish and why it matters. Two to three sentences maximum.
2. **Prerequisites** — What the reader needs before starting. Be specific. List versions, credentials, and dependencies.
3. **Steps** — Numbered steps. One action per step. No compound steps.
4. **Verification** — How the reader knows they succeeded.
5. **Next steps** — Where to go from here. Two to three options maximum.

### Rules

Number all steps. Never use bullet points for procedural steps.

Start each step with an imperative verb.
* Incorrect: "The dependencies need to be installed."
* Correct: "Install the dependencies."

State what the reader should see after each significant step. Do not make them wonder if they did it correctly.

Acknowledge common failure points. If step 3 often fails due to a known issue, say so before the reader encounters it.

Do not skip steps because they seem obvious. What is obvious to the writer is not always obvious to the reader.

### Example

**Do this:**
"3. Enter your API key in the **Key** field and select **Save**. A confirmation message appears at the top of the screen."

**Not this:**
"3. Save your API key."

---

## Content Type 2: API Reference Documentation

### Tone

Neutral, precise, and complete. API reference is not a conversation. It is a contract. Write with zero ambiguity. Avoid personality. Every claim must be verifiable.

### Structure

Every endpoint must document the following:

- **Endpoint** — HTTP method and path
- **Description** — What the endpoint does. One to two sentences.
- **Authentication** — What credentials are required and how to pass them.
- **Request parameters** — Name, type, required or optional, description, and example value for every parameter.
- **Request body** — Schema with field descriptions and example.
- **Response** — Schema with field descriptions and example for success response.
- **Error codes** — Every possible error code with its specific cause and resolution. Never use generic descriptions.
- **Code sample** — A complete, runnable example in at least one language.

### Rules

Document every parameter. Do not skip parameters because they seem self-explanatory.

Document every error code with its specific cause, not just its HTTP meaning.
* Incorrect: "`403` Forbidden — Access denied."
* Correct: "`403` Forbidden — The OAuth token has expired or is invalid. Generate a new token and retry the request."

Use a consistent parameter table format across all endpoints. Do not vary the structure.

Never say "see above" or "see below." Link to the specific section.

If a field is deprecated, say so explicitly and link to the replacement.

If behavior varies by plan or permission level, document each variation explicitly.

### Example Error Code Documentation

| Code | Cause | Resolution |
|------|-------|------------|
| 400 | The request body is malformed or missing a required field. | Check the request body against the schema. Ensure all required fields are present and correctly typed. |
| 401 | The API key is missing from the request header. | Include your API key in the `Authorization` header as a `Bearer` token. |
| 403 | The OAuth token has expired or is invalid. | Generate a new token and retry the request. |
| 429 | The request exceeds the rate limit for your plan. | Check the `Retry-After` header in the response for the wait time, then retry your request. |
| 500 | An unexpected server error occurred. | Retry the request. If the error persists, contact support with the request ID from the response header. |

---

## Content Type 3: Error Messages

### Tone

Direct, helpful, and non-blaming. An error message is received at a moment of failure. The reader is already frustrated. Do not make it worse. Do not blame the user. Do not use exclamation points in error states.

### Structure

Every error message must answer three questions:

1. What happened?
2. Why did it happen?
3. What should the reader do next?

### Rules

Never use "something went wrong." Name the failure specifically.
* Incorrect: "Something went wrong. Please try again."
* Correct: "The request timed out. Check your network connection and try again."

Never use exclamation points in error messages.
* Incorrect: "Invalid input! Please try again!"
* Correct: "The value you entered is not valid. Enter a number between 1 and 100."

Locate the failure accurately. If the system failed, say so. Do not imply the user caused an error they did not cause.
* Incorrect: "Your request could not be processed."
* Correct: "The server could not process your request. Try again in a few minutes."

Use consistent vocabulary across all error messages for the same product. Do not use "generate" in one error and "create" in another for the same action.

If the error has a known resolution, state it. Do not make the reader search for the answer.

Keep error messages under 30 words.

### Error Message Template

```
[What failed] could not [action]. [Reason if known]. [Next step].
```

Example: "Your file could not be uploaded. Files must be under 10 MB. Compress your file and try again."

---

## Content Type 4: Blog Posts and Developer-Facing Articles

### Tone

Conversational, opinionated, and honest. A blog post is not documentation. It has a point of view. Write with your own voice. Share what you know, what you learned, and where you got it wrong. Developer audiences respond to honesty and specificity over polish and generality.

### Structure

Blog posts do not have a required structure, but strong developer posts typically follow this arc:

1. **Hook** — A specific problem, observation, or question. Not a broad statement about the industry.
2. **Context** — Why this matters and to whom.
3. **Body** — The argument, walkthrough, or narrative. Use subheadings to break it up.
4. **Conclusion** — What you learned or recommend. Be direct.

### Rules

Lead with the specific, not the general.
* Incorrect: "AI is changing how we think about documentation."
* Correct: "I spent three months documenting an AI assistant and learned that the hardest part is not writing about what it does. It is writing about what it will not do."

Show your work. Explain how you reached your conclusions. Developer audiences are skeptical of claims without evidence.

Acknowledge limitations and uncertainty. "I am not sure" and "this may not apply to your situation" build more trust than false confidence.

Use subheadings every 300 to 400 words to break up long sections.

Link to sources. If you reference a study, a tool, or another person's work, link to it.

Do not pad. If you have made your point, stop. A 600-word post that says one thing clearly is better than a 1500-word post that says three things vaguely.

---

## Content Type 5: Release Notes

### Tone

Neutral and precise. Release notes are a record. They are not marketing copy. Do not editorialize. State what changed and why it matters to the reader.

### Structure

Every release note entry must include:

- **What changed** — The specific feature, behavior, or fix.
- **Who it affects** — Which users, plans, or configurations are impacted.
- **What to do** — Any action the reader needs to take. If none, say so explicitly.

### Rules

Use active voice. The product or feature performs the action, not a passive construction.
* Incorrect: "Error code `429` is now returned when rate limits are exceeded."
* Correct: "The API now returns error code `429` when rate limits are exceeded."

Be specific about what changed. Do not describe the feature in general terms.
* Incorrect: "Improved performance for large datasets."
* Correct: "Query response times for datasets over 1 million rows have decreased by an average of 40%."

Note breaking changes explicitly and prominently. Use a **Breaking Change** label.

Keep each entry to 120 to 150 words maximum.

Do not use marketing language in release notes.
* Incorrect: "We are thrilled to announce an exciting new feature."
* Correct: "Added support for webhook event filtering."

### Release Note Template

```
**[Feature or fix name]**
[One sentence describing what changed.]
[One sentence describing who is affected and under what conditions.]
[One sentence describing what action the reader should take, if any. If no action is required, write "No action required."]
```

---

## Formatting Standards

### Headings

Use sentence case for all headings. Capitalize only the first word and proper nouns.
* Incorrect: "Getting Started With The API"
* Correct: "Getting started with the API"

Do not use bold, italics, or punctuation in headings.

Use heading levels consistently. Do not skip levels.

### Lists

Use numbered lists for sequential steps.

Use bullet points for non-sequential items.

Keep list items parallel in structure. If the first item starts with a verb, all items start with a verb.

Do not nest lists more than two levels deep.

### Bold and Italics

Use **bold** for UI element names and terms being defined.

Use *italics* for titles of documents, products, or publications.

Do not use bold or italics for emphasis in general prose. If a sentence requires emphasis, rewrite it.

### Links

Use descriptive link text. Never use "click here" or "learn more" as link text.
* Incorrect: "For more information, [click here](#)."
* Correct: "See [Authentication methods](#) for a full list of supported token types."

---

## Inclusive Language

Use gender-neutral language throughout.
- Use "they/them" as a singular pronoun when gender is unknown.
- Avoid "he/she" constructions.

Do not use ableist language.
- Avoid: "sanity check," "blind spot," "crippled," "dummy"
- Use instead: "validation," "gap," "limited," "placeholder"

Do not use terms with exclusionary historical connotations in technical contexts.
- Avoid: "master/slave" for systems relationships
- Use instead: "primary/replica," "leader/follower," "parent/child"

Write for a global audience. Avoid idioms, colloquialisms, and culturally specific references that may not translate.

---

## AI Agent Instructions

When using this style guide as a system reference, follow these directives:

1. Apply the correct content type rules based on what is being written. Do not apply API reference rules to a tutorial.
2. Check every sentence against the banned words list before finalizing output.
3. Check every sentence for em dashes and remove them.
4. Verify all error messages follow the three-question structure: what happened, why, what to do next.
5. Verify all code samples include language identifiers and explanatory comments.
6. Flag any claim that cannot be verified as uncertain rather than stating it as fact.
7. Keep all sentences under 25 words. Flag any sentence that exceeds this limit.
8. Do not add information not present in the source material. If information is missing, say so explicitly.
9. Do not use passive voice. Rewrite passive constructions in active voice before finalizing output.
10. When uncertain about tone, default to precise and neutral rather than conversational.

---

*Developer Content Style Guide v1.0 | Eliana Jain | 2026*
