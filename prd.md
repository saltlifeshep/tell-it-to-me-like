# Product Requirements Document (PRD): tell-it-to-me-like.com

## 1. Introduction & Goals
*   **Product Vision:** To be the go-to platform for experts to simplify their knowledge and create accessible teaching aids for others, leveraging AI to bridge the gap between complex understanding and beginner comprehension.
*   **Core Problem Solved:** Experts struggle to simplify their knowledge for novices; novices struggle to find easily digestible explanations.
*   **Key Differentiator:** AI-driven interactive chat to guide experts in simplifying content ("explain like I'm six"), automated generation of multi-format teaching aids, and a clear monetization path for advanced content.
*   **Primary Goal:** Facilitate the creation and distribution of simplified educational content, grow user base (both experts and learners), and establish a sustainable business model.

## 2. Target Audience & Personas

### 2.1. Personas (Experts & Learners)
*   **Persona 1: "The Patient Grandchild" (Young teaching Older)**
    *   **Name:** Alex (22)
    *   **Background:** Tech-savvy college student, often frustrated explaining basic smartphone functions or app usage to their grandparents.
    *   **Goal:** Wants a simple, shareable guide to help Grandma use her new iPhone without having to repeat themselves constantly.
    *   **Pain Point:** Lack of easily digestible, step-by-step resources tailored for non-tech-savvy seniors.
    *   **Why tell-it-to-me-like.com:** Sees it as a tool to offload repetitive explanations and provide a consistent learning resource.
*   **Persona 2: "The Peer Mentor" (Young teaching Young)**
    *   **Name:** Maya (17)
    *   **Background:** High school student, excels in a particular subject (e.g., advanced math, coding) and wants to help classmates who are struggling.
    *   **Goal:** Create quick, easy-to-understand explainers for complex concepts that her peers can grasp quickly, especially for exam prep.
    *   **Pain Point:** Existing resources are too academic or too simplistic, not hitting the right balance for peer-to-peer learning.
    *   **Why tell-it-to-me-like.com:** Appreciates the AI's ability to simplify and generate different formats for quick consumption (TikTok shorts).
*   **Persona 3: "The Experienced Elder" (Older teaching Younger)**
    *   **Name:** Martha (68)
    *   **Background:** Retired baker, wants to pass down family recipes and traditional cooking techniques to her grandchildren who are just starting to cook.
    *   **Goal:** Provide clear, simple instructions for making classic dishes like "Grandma's Pancakes" that her grandkids can follow without constant calls.
    *   **Pain Point:** Finds it hard to write down instructions in a way that's easy for beginners, and traditional recipe books can be overwhelming.
    *   **Why tell-it-to-me-like.com:** Values the AI's ability to structure and simplify her knowledge into a printable PDF.
*   **Persona 4: "The Community Helper" (Older teaching Older)**
    *   **Name:** Robert (72)
    *   **Background:** Active in a senior community, often helps peers with practical tasks like basic home repairs or understanding new government forms.
    *   **Goal:** Create simple guides for common issues that his friends can refer to, reducing confusion and anxiety.
    *   **Pain Point:** Explaining complex procedures verbally can be tiring, and many online resources are too technical.
    *   **Why tell-it-to-me-like.com:** Sees the value in a platform that can generate easy-to-follow, visual aids for his community.
*   **Persona 5: "The Hobbyist Instructor" (Any age, teaching a niche skill)**
    *   **Name:** Chris (35)
    *   **Background:** Passionate about a niche hobby (e.g., fly tying, vintage camera repair).
    *   **Goal:** Share their expertise with new enthusiasts in an accessible way, potentially building a small online following.
    *   **Pain Point:** Creating high-quality, simplified tutorials from scratch is time-consuming and requires specific media skills.
    *   **Why tell-it-to-me-like.com:** Automates content creation, allowing them to focus on their passion.

## 3. Key Features

### 3.1. Expert User Flow (Content Creation)
*   **Homepage Experience:**
    *   Clear explanation of the service.
    *   Examples of generated output (PDFs, video snippets).
    *   Prominent chat window for topic input.
*   **AI-Guided Content Simplification Chat:**
    *   **Initial Topic Input:** Expert types in a topic (e.g., "how to change a tire").
    *   **Dynamic Questioning:** AI adapts questions based on topic complexity (e.g., ingredient selection for simple topics, specificity questions for technical topics like car make/model).
    *   **Specificity Prompting:** AI always asks about specificity (e.g., year, make, model) to identify upsell opportunities.
    *   **Overwhelming Topic Handling:**
        *   AI detects overly broad/complex topics.
        *   Suggests narrowing down to 2-3 main themes/subtopics with a humorous, non-scolding tone.
        *   Offers a "first crack" summary and asks for confirmation ("Is this a good start?").
    *   **Completion Signal:** "That's it, I'm done" button for simple topics; AI summary and confirmation for complex topics.

### 3.2. Content Generation (n8n Orchestration)
*   **Trigger:** AI chat completion signals n8n to begin content generation.
*   **Free PDF Generation:**
    *   **Content:** General step-by-step guide, limited diagrams.
    *   **Length:** 4-12 pages.
    *   **Source:** n8n orchestrates various AI resources to gather and generate content/context.
    *   **Watermarking:** Initial free PDF is watermarked.
*   **Paid Artifacts Generation (Explainer Videos, TikTok Shorts):**
    *   Triggered upon payment/membership commitment.
    *   n8n orchestrates AI services (e.g., text-to-image, text-to-speech, video synthesis) for content creation.
    *   *Initial Assumption:* All content generation (even for paid artifacts) will be done *after* a user commits to a payment/membership.

### 3.3. Learner User Flow (Content Consumption & List Growth)
*   **Shared Link Experience:**
    *   Learner clicks a link shared by an expert.
    *   Lands on a page explaining the service.
    *   Prompts for email address (and optional name) to download the free PDF.
    *   Option to also send to a family member/friend (requiring their name and email).
*   **Free PDF Delivery:**
    *   After email submission, a link to download the watermarked PDF is emailed to the learner (and optional recipients).
*   **Upsell in Email:**
    *   The email containing the PDF download link will include an upsell offer for:
        *   Unwatermarked PDF.
        *   Other paid artifacts (explainer videos, TikTok shorts).
*   **List Growth:** Email addresses collected from learners are automatically added to a mailing list (via n8n integration with CRM/email marketing service).

### 3.4. Monetization
*   **Free Tier:** Watermarked PDF training aid (requires email signup).
*   **Paid Tiers:**
    *   One-time payment for specific artifacts (e.g., unwatermarked PDF, explainer video).
    *   Membership for access to a library of paid artifacts.
*   **Payment Trigger:** Payment/membership prompt appears when user attempts to access paid content or is presented in the upsell email.
*   **Access Control:** Memberstack integrates with n8n to gate access to paid content.

## 4. Market Research & Competitive Landscape

*   **Disclaimer:** *This section is based on general market understanding and discussions, as real-time web search data for specific metrics (e.g., search volume) was unavailable at the time of writing.*

### 4.1. Market Opportunity:
*   **Growing Need for Simplified Content:** In an increasingly complex world, there's a constant demand for information broken down into easily digestible formats, especially for intergenerational learning or for those new to a topic.
*   **Rise of AI in Content Creation:** AI tools are making content generation more accessible, but often lack the "human touch" of simplification and pedagogical structure.
*   **Niche Focus:** The "explain like I'm six" approach targets a specific, underserved niche within the broader educational content market.
*   **Demographic Push:** The personas highlight a clear need for simplified explanations across various age groups and technical proficiencies. The "young teaching old" and "old teaching young" dynamics are particularly strong.

### 4.2. Competitors (Direct & Indirect):
*   **Indirect Competitors (Broad Learning Platforms):**
    *   **YouTube:** Vast repository of "how-to" videos, but quality and simplification vary wildly. Discoverability of truly simplified content can be challenging.
    *   **Google Search:** Primary entry point for information, but results often lead to complex articles or forums.
    *   **Online Course Platforms (e.g., Coursera, Udemy):** Offer structured learning, but typically at a deeper, more academic level, not focused on "explain like I'm six."
    *   **Blogs/Articles:** Many offer tutorials, but again, simplification varies, and they lack interactive content generation.
    *   **TikTok/Instagram Reels:** Short-form video, but often lacks depth or structured explanation.
*   **Direct Competitors (AI Content Generation):**
    *   **General AI Writing Tools (e.g., Jasper, Copy.ai):** Can generate text, but require significant human prompting and editing to achieve the "explain like I'm six" style and pedagogical structure. They don't specialize in teaching aids.
    *   **AI Video Generators (e.g., Synthesys, Pictory):** Can create videos from text, but lack the interactive AI chat for content simplification and the specific focus on teaching aids.
    *   **No clear direct competitor that combines AI-driven interactive simplification, multi-format teaching aid generation, and a clear monetization model for this specific niche.**

### 4.3. Differentiation:
*   **AI-Guided Simplification:** The core differentiator is the interactive AI chat that actively helps experts simplify their knowledge, rather than just generating content from raw input.
*   **Multi-Format Output:** Offering PDFs, explainer videos, and TikTok shorts from a single input streamlines content creation for experts.
*   **Targeted Niche:** Focus on "explain like I'm six" for intergenerational and beginner learning.
*   **Monetization Model:** Clear path for experts to monetize their simplified content, and for the platform to generate revenue from paid artifacts.

## 5. SWOT Analysis

### 5.1. Strengths (Internal, Positive)
*   **Unique Value Proposition:** Addresses a clear market gap for simplified, AI-generated teaching aids.
*   **Scalability:** AI-driven content generation allows for high scalability without linear increase in manual effort.
*   **User-Friendly Approach:** The "explain like I'm six" philosophy and adaptive AI chat make it accessible for experts.
*   **Diverse Output Formats:** Caters to different learning styles and platforms (PDF, video, short-form video).
*   **Strong Monetization Potential:** Clear free-to-paid conversion path.
*   **Growth Strategy:** Built-in virality through shared links and email list building.

### 5.2. Weaknesses (Internal, Negative)
*   **AI Accuracy & Quality Control:** Reliance on AI for content generation means potential for inaccuracies, generic content, or lack of nuance. Requires robust post-generation review.
*   **"Costly Generation" Management:** Detecting and managing the cost of AI API calls for content generation, especially for paid artifacts, needs careful implementation and monitoring.
*   **User Adoption:** Convincing experts to use a new platform for content creation when existing (albeit less efficient) methods are available.
*   **Diagram/Visual Generation:** Generating truly useful and context-specific diagrams/visuals automatically can be challenging for AI.
*   **Niche Limitation:** While a strength, the niche focus might limit initial broad appeal compared to general AI content tools.

### 5.3. Opportunities (External, Positive)
*   **Growing AI Capabilities:** Rapid advancements in AI (text-to-image, text-to-video, LLMs) will enhance content quality and diversity.
*   **Demand for Micro-Learning:** Short-form video and simplified content align with modern learning trends.
*   **Intergenerational Digital Divide:** A persistent need for tools that bridge the gap between tech-savvy and non-tech-savvy individuals.
*   **Partnerships:** Potential for partnerships with educational institutions, community centers, or content creators.
*   **Expansion into Other Languages:** Global market potential.

### 5.4. Threats (External, Negative)
*   **Rapidly Evolving AI Landscape:** New AI tools could emerge quickly, offering similar or superior capabilities.
*   **"Good Enough" Free Alternatives:** Users might stick with existing free (though less efficient) methods like YouTube or manual content creation.
*   **Content Quality Perception:** If AI-generated content is perceived as low quality or generic, it could damage reputation.
*   **Copyright/Attribution Issues:** Sourcing content via AI from the web could lead to copyright concerns if not managed carefully.
*   **User Fatigue with AI Chatbots:** Users might get tired of interacting with chatbots if the value proposition isn't consistently high.
*   **Data Privacy Concerns:** Handling user emails and potentially sensitive content requires robust privacy measures.

## 6. Technology Stack
*   **Frontend:** Astro
*   **Hosting:** Netlify
*   **Membership/Payments:** Memberstack
*   **Workflow Automation/AI Orchestration:** n8n

## 7. Future Considerations
*   Refining "costly generation" detection and coordination with payment.
*   Continuous improvement of AI chat for topic narrowing and content simplification.
*   Exploring advanced AI for diagram and visual asset generation.
*   Implementing robust content review and feedback mechanisms.

## 8. Poking Holes & Critical Thoughts

*   **AI Hallucinations/Accuracy:** This is a significant risk. How will we ensure the AI-generated content (especially for complex or technical topics) is accurate and doesn't "hallucinate" facts? A human review step might be necessary, which adds friction to the expert's workflow.
*   **Diagram Quality:** "Limited diagrams" for the free PDF is a good start, but for paid content, high-quality, context-specific visuals are crucial. Relying solely on AI for this can be challenging. Will there be a library of pre-approved simple diagrams, or will n8n integrate with more advanced visual AI?
*   **Content Uniqueness:** If n8n is pulling from "various AI resources," how do we ensure the generated content isn't just a rehash of publicly available information, especially for common topics? The "explain like I'm six" angle helps, but originality is key for perceived value.
*   **Expert Engagement:** Why would an expert choose to spend time teaching the AI to simplify their knowledge when they could just create content directly on YouTube or TikTok? The value proposition needs to be very strong (e.g., "save hours of content creation," "reach a new audience").
*   **Monetization Conversion:** The upsell in the email is good, but what's the conversion rate expectation? How compelling will the paid artifacts be to justify the cost, especially if the free PDF is already quite useful?
*   **User Experience for Overwhelming Topics:** While the "first crack" summary is a good idea, guiding a user to narrow down a truly complex topic (like "history of war in the Middle East") without frustrating them will be a UX challenge. The AI needs to be very adept at suggesting meaningful subtopics.
*   **Scalability of Paid Content Generation:** If paid artifacts require significant AI processing (e.g., video rendering), how will n8n handle a large volume of requests without becoming a bottleneck or incurring prohibitive costs?
