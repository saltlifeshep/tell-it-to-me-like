# Project Plan: tell-it-to-me-like.com

## Phase 1: Foundation & Core MVP (Minimum Viable Product)
*   **Goal:** Establish the basic infrastructure and deliver the core free PDF generation and delivery flow.
*   **Tasks:**
    1.  [x] **Project Setup:**
        *   [x] Initialize Astro project.
        *   [x] Configure Netlify for continuous deployment.
    2.  [ ] **Frontend (Astro):**
        *   [x] Design and implement homepage with explanation, examples, and a prominent chat input area.
        *   [x] Create basic chat UI for expert input (initial topic submission).
        *   [x] Develop a simple landing page for learners to enter email for PDF download.
    3.  [ ] **Backend/Workflow (n8n):**
        *   [x] Set up n8n instance (local for development, then deployable).
        *   [ ] Create a basic n8n workflow to:
            *   [x] Receive topic input from Astro frontend.
            *   [ ] Trigger a placeholder AI content generation (e.g., simple text response).
            *   [ ] Generate a basic, text-only PDF (no diagrams, no watermarking initially).
            *   [ ] Send an email with a download link for the PDF.
            *   [ ] Capture email addresses for list growth (store temporarily or in a simple database).

## Phase 2: AI Chat & Content Refinement
*   **Goal:** Enhance the AI interaction for experts and improve the quality of the free PDF.
*   **Tasks:**
    1.  [ ] **AI Chat Logic:**
        *   [ ] Implement dynamic questioning based on topic complexity.
        *   [ ] Develop logic for "specificity prompting" (e.g., year/make/model).
        *   [ ] Implement "overwhelming topic" detection and suggestion for narrowing down.
        *   [ ] Refine "first crack" summary and confirmation flow.
        *   [ ] Implement "That's it, I'm done" and "Add more" buttons.
    2.  [ ] **PDF Generation Improvement:**
        *   [ ] Integrate AI services (via n8n) for more sophisticated content generation.
        *   [ ] Add basic diagram placeholders to the PDF.
        *   [ ] Implement watermarking for the free PDF.

## Phase 3: Monetization & Paid Content
*   **Goal:** Integrate payment and membership, and enable generation of paid artifacts.
*   **Tasks:**
    1.  [ ] **Membership & Payments (Memberstack):**
        *   [ ] Integrate Memberstack for user authentication and payment processing.
        *   [ ] Set up membership tiers and one-time payment options.
    2.  [ ] **Upsell & Access Control:**
        *   [ ] Develop the upsell offer within the PDF delivery email.
        *   [ ] Implement logic to gate access to paid content via Memberstack.
        *   [ ] Create dedicated pages/flows for purchasing paid artifacts.
    3.  [ ] **Paid Artifact Generation (n8n):**
        *   [ ] Integrate n8n with AI services (e.g., text-to-video/image services) for explainer video and TikTok short generation (initial versions).
        *   [ ] Develop workflows to deliver paid artifacts upon successful payment.

## Phase 4: Polish, Optimization & Growth
*   **Goal:** Refine the user experience, optimize performance, and strengthen growth mechanisms.
*   **Tasks:**
    1.  [ ] **UI/UX Enhancements:**
        *   [ ] Improve overall design and responsiveness of the Astro frontend.
        *   [ ] Enhance chat interface for better user experience.
    2.  [ ] **Content Quality & Accuracy:**
        *   [ ] Optimize AI prompts and models for improved content quality and accuracy.
        *   [ ] Implement a human review/feedback loop for AI-generated content (if feasible).
    3.  [ ] **Scalability & Cost Management:**
        *   [ ] Monitor and optimize n8n workflows for cost-efficiency, especially for "costly generations."
        *   [ ] Address potential bottlenecks for high-volume content generation.
    4.  [ ] **Marketing Integration:**
        *   [ ] Integrate n8n with a chosen email marketing service (e.g., Mailchimp, ConvertKit) for automated list growth.
