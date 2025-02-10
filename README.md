# The Software Architecture Guild Architectural Kata by O'Reilly, February 2025

## Team members

- [Ilya Hardzeenka](https://www.linkedin.com/in/ilya-hardzeenka/)
- [Ksenia Bernat](https://www.linkedin.com/in/kseniya-bernat-342900104/)
- [Denis Klimenko](https://www.linkedin.com/in/den1sklimenko/)
- [Mikalai (Nick) Herman](https://www.linkedin.com/in/gekola/)
- [Oleg Zubchenko](https://www.linkedin.com/in/rgbd-me/)

## Table of Contents

## Welcome

Welcome to the [Software Architecture Guild](https://software-architecture-guild.com/) Architectural Kata run by O'Reilly in February 2025.

We are the Software Architecture Guild — a group of seasoned software architects who have spent years working together, honing our craft, and developing a shared approach to software architecture. During this time, we leveled up our skills and learned invaluable lessons about what it takes to succeed in this field.

Our mission is to design and shape the foundation upon which software architectures evolve, AI-driven insights emerge, and intelligent solutions are built.

As architects, we understand the power and potential of AI to transform industries, drive efficiencies, and unlock new possibilities. We are at the forefront of designing, securing, and optimizing software ecosystems to fully leverage AI capabilities and create adaptive, scalable, and intelligent systems.

In our work we mainly utilize following techniques:

- [Viewpoints and Perspectives Framework by Rozanski,Woods](https://www.viewpoints-and-perspectives.info/)
- [C4 Modeling approach](https://c4model.com/)

## Business Case

### Background

Certifiable, Inc. is a recognized leader in software architecture certification, providing accredited certification to software architects primarily in the U.S. Due to recent regulatory changes, international markets including the U.K., Europe, and Asia now require software architects to be certified, significantly increasing the demand for certification services. With this anticipated expansion, Certifiable, Inc. is facing a substantial surge in certification requests—estimated to grow 5-10 times their current volume. The existing manual processes for test grading and certification management are proving to be inefficient and unsustainable at this scale.

Given this challenge, the company is exploring how Generative AI can be integrated into their current system to optimize operations, improve efficiency, and maintain high certification standards while managing cost constraints.

### Market Opportunity

The global demand for certified software architects is accelerating due to government regulations and industry requirements.

- **Market Size & Growth**: The U.S. alone has over 176,000 software architects, with 300,000 job openings. Internationally, the number of software architects is estimated to be around 600,000, and the industry is projected to grow by 21% over the next four years.
- **Revenue Potential**: Certifiable, Inc. currently processes *200 candidates per week* at a fixed certification cost of *$800*. With the expected increase in demand, this number could rise to *1,000-2,000 candidates weekly*, translating into an annual revenue increase from certification fees alone.
- **Competitive Advantage**: As the market leader, Certifiable, Inc. holds over 80% market acceptance in the U.S. and a dominant presence in international markets. Successfully implementing AI-driven automation will strengthen its position as the most efficient and reliable certification provider globally.

### Objective

The primary objective is to modernize the SoftArchCert system by leveraging Generative AI to streamline the certification process while maintaining accuracy, reliability, and cost-effectiveness.

#### Key Goals

- **Enhance Efficiency**: Reduce manual workload by automating grading processes, candidate feedback, and test modifications.
- **Maintain Accuracy & Quality**: Ensure AI-driven grading maintains the high standards required for certification validity.
- **Scale Operations**: Support a five to tenfold increase in certification candidates without overwhelming human graders.
- **Cost Optimization**: Implement AI solutions that align with budget constraints while providing maximum efficiency.

### Stakeholders

Several key stakeholders will be impacted by this initiative:

#### Internal Stakeholders

- **Certifiable, Inc. Leadership**: Executive management responsible for strategic direction and investment in AI-driven improvements.
- **Software Architect Graders**: Expert software architects who grade aptitude tests and case studies; their workload and processes will be affected by AI-driven automation.
- **System Administrators**: Responsible for maintaining certification systems and implementing AI-enhanced features.
- **Technology Team**: Architects and developers responsible for integrating AI into the SoftArchCert system.

### External Stakeholders

- **Certification Candidates**: Software architects seeking certification who will experience a potentially faster, AI-enhanced grading process.
- **Accreditation Bodies (SALB & International Licensing Boards)**: Organizations responsible for maintaining certification integrity and compliance.
- **Employers & Hiring Managers**: Companies that rely on Certifiable, Inc. certifications for hiring and verifying software architects.

By addressing these stakeholder needs and aligning with market opportunities, Certifiable, Inc. can ensure its continued dominance in the certification industry while meeting the demands of an expanding global market.

### Original requirements

For the original requirements please follow [Original Requirements](requirements/original_requirements.md)

## Current System Overview

### Functional Viewpoint

> *Describes the system’s functional elements, their responsibilities, interfaces,
> and primary interactions*

Since we already have an established system, we believe the best way to describe its existing functionality is through User Journey Maps and a System Blueprint.

We have identified several personas who interact with the system and actively participate in the business process:

- **Candidate**
  A software architect seeking certification through Certifiable, Inc. Candidates must pass two tests: an aptitude test and an architecture submission. They rely on timely grading, accurate feedback, and certification validation to advance their careers.
- **Expert**
  An employed expert software architect responsible for grading certification exams and providing detailed feedback to candidates. They are freelance contractors paid per hour and play a crucial role in ensuring the integrity of the certification process.
- **Designated Expert**
  A senior expert software architect with additional responsibilities beyond grading. They have the authority to modify certification tests, create or update case studies, and ensure that certification standards evolve with industry practices.
- **Administrator**
  A Certifiable, Inc. staff member responsible for managing expert software architects, maintaining system access, and ensuring smooth certification operations. They oversee expert profiles, system credentials, and help facilitate AI-driven enhancements.
- **External HR**
  Hiring managers and recruiters from various companies who rely on Certifiable, Inc.'s certifications to verify the qualifications of software architects. They use the certification database to validate credentials and make informed hiring decisions.

#### Candidate Journey Map

1. Registration & Application – The candidate registers on the Certifiable, Inc. platform and submits an application for certification.
2. Aptitude Test (Test 1) – The candidate takes a timed multiple-choice and short-answer aptitude test. Multiple-choice questions are auto-graded, while expert software architects review short-answer responses.
3. Test Results & Eligibility – If the candidate scores 80% or higher, they receive an invitation to the architecture submission test. If they fail, they receive detailed feedback and can reattempt.
4. Architecture Submission (Test 2) – The candidate downloads a case study, designs a software architecture solution, and submits their work within two weeks.
5. Evaluation & Feedback – Expert software architects review the submission, grade it based on set criteria, and provide feedback.
6. Certification & Verification – If the candidate passes both tests, they receive official certification, which is stored in the database for employer verification. If they fail, they can reapply for Test 2.

![Diagram](current_state/functional_viewpoint/candidate_journey_map.png)

#### Expert Journey Map

1. Profile Setup & Access – The expert software architect is onboarded by Certifiable, Inc. and gains access to the grading system. They can update their profile and set availability.
2. Test 1 Grading (Aptitude Test) – Experts review and grade short-answer responses manually. They provide detailed feedback and ensure grading accuracy based on established evaluation criteria.
3. Test 2 Grading (Architecture Submission) – Experts assess architecture submissions based on predefined rubrics. They spend an average of 8 hours per submission, ensuring fair and precise evaluation. Experts offer candidates detailed explanations for incorrect answers, areas of improvement, and scoring justifications to help them understand their results.
4. Test & Case Study Improvements – Designated experts periodically analyze test performance, identify problematic questions, and propose modifications or new case studies to keep the certification process relevant.

![Diagram](current_state/functional_viewpoint/expert_journey_map.png)

#### Designated Expert Journey Map

A Designated Expert has all the responsibilities of a regular Expert Software Architect, including grading aptitude tests, reviewing architecture submissions, providing feedback, and contributing to certification system updates.

1. Getting Access – The designated expert receives elevated access role from the system administrator.
2. Review Suggested Improvements from Experts – They analyze feedback and improvement suggestions submitted by expert graders regarding test questions, case studies, and grading inconsistencies. They assess recurring issues in test performance data, such as frequently failed questions.
3. Maintain Tests - Based on expert feedback and industry advancements, designated experts update aptitude test questions. They remove outdated or problematic questions and introduce new ones to reflect emerging software architecture trends. Changes are tested to ensure balance and difficulty consistency across certification exams.
4. Maintain Case Studies - Designated experts develop new architecture case studies to prevent content leaks and ensure the certification process remains challenging and relevant. They modify existing case studies to incorporate modern design patterns, industry best practices, and evolving regulatory requirements. Outdated or redundant case studies are deleted to maintain a streamlined and effective certification process.

![Diagram](current_state/functional_viewpoint/designated_expert_journey_map.png)

#### Service Blue Print

> *A **Service Blueprint** is a detailed visual representation of a service process, illustrating interactions between users, system components, and backend processes. It provides a structured framework for understanding how a service functions by mapping out key elements such as customer actions, employee roles, supporting systems, and process flows.*

![Diagram](current_state/functional_viewpoint/service_blueprint.png)

**Key takeaways**:

1. Grading the Aptitude Test takes approximately 3 hours. This process involves two primary tasks: evaluating answers and providing comments for incorrect responses. Since no specific data is available, **we assume an equal time distribution of 50% for grading and 50% for feedback**.
2. Grading the Architecture Submission takes approximately 8 hours. This involves three key tasks: reviewing the candidate's submitted architecture, assessing it against predefined criteria, and writing detailed feedback. In the absence of precise data, **we assume an equal time distribution of 33% for understanding the submission, 33% for grading, and 33% for providing feedback**.
3. While reducing candidate wait times is possible, it is entirely dependent on the time required for test validation and grading. Therefore, wait time improvements cannot be addressed in isolation.

### Context Viewpoint

> *Describes the relationships, dependencies, and interactions between the system and its environment (the people, systems, and external entities with which it interacts).*

### Informational Viewpoint

> *Describes the way that the architecture stores, manipulates, manages, and distributes information.*

Understanding what data is stored and where is critical for the successful implementation of AI-driven enhancements. any ML or AI system. Unfortunately, we have limited information about the data structures used in the system. The provided diagrams give insight into the names of data objects and their relationships, but their exact contents remain unknown, requiring us to make assumptions.

> [!NOTE]
> *If the existing data model differs from our assumptions, it will introduce a prerequisite implementation step before any proposed AI-related changes can be implemented. This step would involve aligning the data model with the necessary structure to support AI integration.*

The diagram below represents our best estimation of what the data model should look like.

![Diagram](current_state/informational_viewpoint/data_model.png)

We will not describe every object in the diagram, but we will focus on two key ones:

- **Graded Aptitude test submission**: is a historical dataset, which contains following information:
  - Aptitude test questions as they were at the time of test validation
  - Multiple choice answers and grades
  - Short Answers, Grades and Expert Feedback
  - **We assume that Grade and Feedback are stored per each Question/Answer**
  - Expert ID and Time it took validate test and provide feedback

- **Graded Architecture submission**: is a historical dataset, which contains following information:
  - Case Study and Grading Criteria as they were at the time of test validation
  - Grades based on each Criteria and Expert Feedback
  - **We assume that Grade and Feedback are stored per each Criteria**
  - Expert ID and Time it took validate test and provide feedback

**We assume that data from these datasets is never deleted and contains submissions, grades, and feedback for 120,000 candidates** who have already completed the certification process.

### Cost Perspective

> *Evaluates the financial impact of architectural decisions, balancing implementation, operation, and scalability costs with business value.*

Candidates pay $800 per certification. The validation process alone takes 11 hours of an Expert’s time, who is compensated at $50 per hour, resulting in a $550 validation cost, which accounts for 68% of the test fee.

Additionally, there are other costs to consider, including hosting expenses, designated experts’ time for maintaining tests and case studies, and administrator salaries. While not all candidates will pass Test 1, potentially reducing average validation costs, relying on failure rates as a cost-saving strategy is not practical. Therefore, **we assume the full validation cost applies to every candidate** to ensure accurate financial planning.

### Quality Perspective

> *Focuses on ensuring the system meets defined Service Level Agreements (SLAs) by maintaining reliability, performance, accuracy, and user expectations.*

Here are the requirements provided:

- As a recognized leader in certification, accuracy of tests, case studies, and grading is fundamental and inaccurate grading can result in a
  candidate not getting or maintaining a job and can impact a candidate's career.
- Inaccurate or misleading certification exams and case studies can undermine the credibility of the company’s current standing in the
  marketplace, so accuracy of the certification process is vital for the success of the company.

Given the lack of additional information, we must make the **following assumptions**:

- **There are no existing quality control measures in place to ensure grading accuracy.**
- **There is no formal appeals process that allows candidates to challenge grading errors made by Experts.**

## Assumptions

<mark>
- For the **3 hours** an Expert spends on **Aptitude Test validation**, we assume the time is evenly split: **50% for grading** and **50% for providing feedback**.
- For the **8 hours** an Expert spends on **Case Study validation**, we assume the time is evenly distributed: **33% for understanding the submission, 33% for grading, and 33% for providing feedback**.
- !!! We assume the system **automatically tracks** the time an Expert spends on validating tests and **stores this information** in a designated location.
- We assume there is **no established retention period**, and the database **stores graded answers and architecture submissions** of **120,000 candidates** who have already completed the certification process.
- We assume that for the Aptitude Test, the **Grade and Feedback** are recorded **for each Question/Answer**, whereas for the Case Study Test, they are recorded **for each Criterion**.
- We assume the **full validation cost of $550** applies to **every candidate**, regardless of pass or fail rates.
- We assume there are **no established quality control measures** to verify grading accuracy.
- We assume there is **no formal appeals process** that allows candidates to challenge grading errors made by Experts.
</mark>

## Challenges and Opportunities

### Scalability is a Major Challenge

The company currently employs *300 Experts* to validate tests for *200 candidates per week*. Scaling up to *1,000 candidates per week* would require either *longer wait times* (which is unacceptable) or *hiring significantly more Experts*. Hiring more Experts would also necessitate additional *managerial roles and support staff* (e.g., Administrators, Accountants, HR personnel), further *increasing operational costs*. As a result, *the cost per test would continue to rise*, negatively impacting profitability.

#### <mark>Opportunity: Investing in **automation** is essential to ensure the company's long-term viability</mark>

### High Cost Model

Currently, the company spends *$550 per test validation*, which accounts for *68% of the $800 certification fee*. This is a *significant expense*, and the *primary cost driver* is the time spent by Experts on validation. Reducing validation time is *key to lowering costs*, and AI can play a major role in *optimizing productivity*.

#### <mark>Opportunity: AI-driven productivity enhancements can significantly **reduce validation time**, leading to **lower costs per test** and increased **operational efficiency**</mark>

### Current Expert Compensation Model Discourages Efficiency

Experts are *paid per hour*, meaning there is *no incentive* for them to work faster or process more tests. AI assistance can only succeed *if Experts are motivated* to use it effectively.

A better approach would be a *per-test payment model* instead of hourly pay.

- Currently, grading an *Aptitude Test* takes *3 hours*, earning an Expert *$150* ($50 per hour).
- If AI-assisted grading *reduces validation time to 1.5 hours*, and we *pay $100 per test*, an Expert could validate *two tests in the same 3-hour period*, earning *$200 instead of $150*.
- At the same time, the *company’s cost per test* would decrease from *$150 to $100*, improving efficiency and profitability.

#### <mark>Opportunity: Transitioning to a **per-test payment model** would incentivize Experts to work faster and maximize efficiency, benefiting both Experts and the company</mark>

### High-Quality Expectations Limit Full Automation

Given the strict *accuracy and reliability requirements*, fully automating the grading process is *not viable*. A human *must remain in control* to make final grading decisions. Instead of *replacing Experts*, AI should function as an *assistant*, helping them *validate tests faster and with greater accuracy*.

#### <mark>Requirement: AI should be used as an **expert assistant**, speeding up grading rather than replacing human decision-making</mark>

### Lack of a Measurable Grading Quality Process

Despite high expectations for grading quality, there is *no formalized process to measure it*. Establishing a *quality baseline* is crucial before making system changes. Experts already make mistakes, and incorporating *candidate feedback loops* is essential for assessing grading accuracy. A *human-only baseline* must be established to *track improvements* as AI-assisted grading is introduced.

#### <mark>Requirement: A **quality control process** must be implemented before system improvements, ensuring that grading accuracy can be measured and improved over time</mark>

### No Defined Process for Tracking Validation Time

There is *no mention of how validation time is currently tracked*, yet it is a key efficiency metric for AI-assisted improvements. A proper *measurement system* must be put in place to ensure progress in *reducing validation time*.

#### <mark>Requirement: **Tracking validation time** is critical for evaluating AI effectiveness and must be established before automation is introduced</mark>

## Proposed Solutions

### Overview

### Solution 1

#### Architecture

Diagrams + ADRs

#### Implementation Milestones

### Solution 2

#### Architecture

Diagrams + ADRs

#### Implementation Milestones

### Solution 3

#### Architecture

Diagrams + ADRs

#### Implementation Milestones

## Final words
