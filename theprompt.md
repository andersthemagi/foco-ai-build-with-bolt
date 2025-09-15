Generated using Gemini 2.5 Flash. 

---

## The Prompt

**Role:** You are an expert web developer specializing in creating modern, sleek, and accessible single-page applications using React and Tailwind CSS. You are to build a virtual birthday card website.

**Task:** Create a single-page React application for the "Fort Collins AI for Everyone" group. The website will serve as a platform for people to share kind messages, learn about the group's impact, and show appreciation for its sponsors and speakers. The design should be modern, polished, and inspired by the provided logo's color palette.

**Requirements:**

* **Technology Stack:** The application must be built using **React** for the front-end and **Tailwind CSS** for styling.
* **Database:** Use **Supabase** for backend operations. The application must include functionality to insert new messages into a `messages` table and fetch approved messages from the same table. The `messages` table schema will now include a `type` column to distinguish between "community," "sponsor," or "speaker" messages, and an optional `image_url` column for sponsor logos.
* **User Interface (UI):** The website must be a single-page experience, featuring:
    * A prominent hero section with a brief welcome message and two calls-to-action: "Send a Message" and "Join Us on Meetup."
    * The "Send a Message" button must open a modal containing a form.
    * The "Join Us on Meetup" button must link to `https://www.meetup.com/fort-collins-ai-for-everyone-rmaiig/`.
    * A section below the hero dedicated to the **"About Us"** description. This section will also display key group statistics like "Number of Members" and "Meetings in 2025" to highlight the group's impact.
    * A separate section that displays all the approved messages submitted by users. This section must be visually split into two distinct subsections: **"Sponsor & Speaker Messages"** and **"Community Messages"**. Sponsor and Speaker messages must be prominently displayed and include the associated logo image from the `image_url` field.
* **Form Functionality:**
    * The message submission form must collect the user's **first name**, **last name**, **company (optional)**, and a **message**. The message should be limited to the length of a tweet (280 characters).
    * Upon form submission, the message must be inserted into the Supabase `messages` table with a `status` column set to "pending" and the `type` column set to "community."
* **Backend Logic:**
    * When fetching messages to display on the page, the query must only retrieve messages where the `status` column is set to "approved."
    * The application must make two separate fetches to the Supabase database: one for messages where `type` is "sponsor" or "speaker," and another for messages where `type` is "community."
* **Design & Accessibility:**
    * The visual design should match the warm, orange-yellow and gray color scheme of the provided logo.
    * Include tasteful, subtle animations for elements as they are rendered on the page to enhance the user experience.
    * The entire website must adhere as closely as possible to the **WCAG 2.2 AA guidelines**, ensuring a high level of accessibility for all users.
    * The design should be fully responsive for desktop, tablet, and mobile devices.

**Instructions:**

1.  Begin by scaffolding a React project using Vite.
2.  Set up Tailwind CSS for styling.
3.  Create the main `App.js` component to handle the single-page layout.
4.  Develop a dedicated component for the hero section with the two call-to-action buttons.
5.  Create a separate component for the message form modal.
6.  Build a dedicated component for the "About Us" section that includes placeholder text for the group description and for displaying the key stats (e.g., using a visually appealing list or cards).
7.  Create a component for displaying the list of approved messages. This component should fetch messages, then render separate sub-components for **Sponsor/Speaker** messages (including image display) and **Community** messages.
8.  Write all necessary Supabase query functions, including the two distinct fetch calls to separate sponsor/speaker and community messages.
9.  Ensure all interactive elements, such as buttons and form inputs, are keyboard-navigable and have proper ARIA attributes for screen readers.
10. Add subtle animations for elements like messages appearing on scroll or the form modal entering the screen.
11. Do not include any approval or denial functionality in the front-end; this will be handled separately. The front-end's sole purpose is to submit new community messages and display all approved messages.
