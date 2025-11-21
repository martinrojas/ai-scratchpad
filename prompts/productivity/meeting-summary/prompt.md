
**Objective:** Generate comprehensive meeting notes from a provided call transcript, and accurately answer follow‑up questions using only the transcript content.

**Tasks:**

1. **Analyze the Transcript:**
   * Thoroughly read the call transcript to understand the discussion's context and content.
   * Identify main topics, key decisions, and any action items or follow‑up tasks.
   * Track participants’ names and their contributions.

2. **Generate Meeting Notes:**
   * Structure the notes into clear and concise sections, following this template:
     * **Meeting Title:**
     * **Date & Time:**
     * **Attendees:**
     * **Agenda:** (include only if explicitly mentioned)
     * **Discussion Summary:**
       * [Topic]: [Summary with bullet points or short paragraphs]
       * ...
     * **Action Items:**
       * [Person Assigned]: [Task] – [Due Date or [Unclear in Transcript]]
       * [Unassigned]: [Task] – [Due Date or [Unclear in Transcript]]
   * Ensure the notes are accurate, complete, and limited to what is stated in the transcript.

3. **Answer Follow‑Up Questions:**
   * Respond only with information from the transcript.
   * Do not invent or bring in outside knowledge.
   * If an answer cannot be found, clearly state: “The transcript does not provide this detail.”
   * When possible, attribute answers to the specific participant(s) who made the relevant statement.

**Guidelines:**
* Maintain a professional, objective tone.
* Prioritize clarity, conciseness, and readability.
* Do not infer or create new tasks, agenda points, or decisions beyond the transcript.
* If information is ambiguous or missing, mark it as [Unclear in Transcript].

**Example:**

**Meeting Title:** Project Brainstorm Session

**Date & Time:** 2024-10-29, 10:00 AM PST

**Attendees:** John Smith (Project Manager), Jane Doe (Designer), David Lee (Engineer)

**Agenda:**
* Discuss initial project concepts
* Brainstorm potential design approaches
* Identify technical requirements

**Discussion Summary:**
* **Initial Project Concepts:** The team explored three main concepts... [Summarize key points]
* **Potential Design Approaches:** Jane presented two design options... [Summarize key points]
* **Technical Requirements:** David outlined the key technical considerations... [Summarize key points]

**Action Items:**
* Jane Doe: Create mockups for both design options – 2024-11-05
* David Lee: Research feasibility of proposed technical solutions – 2024-11-05
* John Smith: Schedule follow‑up meeting to review designs and technical feasibility – [Unclear in Transcript]
* [Unassigned]: Finalize project scope based on design and technical feasibility – [Unclear in Transcript]

---
# V1 Prompt

**Objective:**  Generate comprehensive meeting notes from a provided call transcript.

**Tasks:**

1. **Analyze the Transcript:**
    * Thoroughly read the call transcript to understand the discussion's context and content.
    * Identify the main topics covered, key decisions made, and any action items or follow-up tasks assigned.
    * Pay close attention to the participants' names and their roles in the conversation.

2. **Generate Meeting Notes:**
    * Structure the notes into clear and concise sections, using the following template:
        * **Meeting Title:** 
        * **Date & Time:** 
        * **Attendees:**
        * **Agenda:**
        * **Discussion Summary:** 
            *  [Topic 1]: [Summary with bullet points or short paragraphs]
            *  [Topic 2]: [Summary with bullet points or short paragraphs]
            *  ...
        * **Action Items:**
            * [Person Assigned]: [Task] - [Due Date]
            * [Person Assigned]: [Task] - [Due Date]
            * ...
        * **Unassigned Next Steps:**
            * [Task or Decision] - [Notes or Context] 
            * ... 
    * Ensure the notes are accurate, complete, and faithfully reflect the call transcript's content.

**Guidelines:**

* Maintain a professional and objective tone.
* Be clear, concise, and focused on essential information.
* Prioritize readability and ease of understanding.
* If a due date for an action item cannot be determined from the transcript, indicate that it needs to be clarified.

**Example:**

**Meeting Title:** Project Brainstorm Session

**Date & Time:** 2024-10-29, 10:00 AM PST

**Attendees:** John Smith (Project Manager), Jane Doe (Designer), David Lee (Engineer)

**Agenda:** 
* Discuss initial project concepts
* Brainstorm potential design approaches
* Identify technical requirements

**Discussion Summary:**

* **Initial Project Concepts:** The team explored three main concepts... [Summarize key points]
* **Potential Design Approaches:**  Jane presented two design options... [Summarize key points]
* **Technical Requirements:** David outlined the key technical considerations... [Summarize key points]

**Action Items:**

* **Jane Doe:** Create mockups for both design options - 2024-11-05
* **David Lee:** Research feasibility of proposed technical solutions - 2024-11-05
* **John Smith:** Schedule follow-up meeting to review designs and technical feasibility - [Needs Clarification]

**Unassigned Next Steps:**

* Finalize project scope based on design and technical feasibility assessments.