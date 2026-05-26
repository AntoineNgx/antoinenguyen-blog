# **The SaaS Implementation/Migration That Actually Sticks**

### Most SaaS Migrations Follow a Plan. The Ones That Succeed Follow a Structure.

Every SaaS migration has a plan. A Gantt chart. A kickoff deck. A project manager tracking tasks in a board somewhere.

And yet, most migration failures don't come from missing plans. They come from missing phases, entire categories of work that never made it into the scope because nobody thought to put them there.

After years of leading SaaS migration and implementation projects across pharma, biotech, and enterprise clients, I've built a framework around the phases, activities, and milestones that consistently separate migrations that stick from migrations that silently collapse after go-live.

This is not a methodology pitch. It's a field guide for what actually needs to happen, in what order, and why skipping any of it costs you later.

### **Before Phase 1 even starts: the scoping nobody does properly.**

Most migrations begin with a cost estimate and a timeline. That's already too late.

Before any project phase starts, there's a pre-project scoping stage that determines whether the entire engagement is set up for success or for a slow-motion budget overrun. This is where account managers, customer success managers, and project managers need to be in the same room, literally or figuratively, asking the right questions.

These aren't generic discovery questions. They're structural:

How many functional teams will use the platform, what's each team's business use case, and how many users per team? What's the total record count across core objects like accounts, contacts, opportunities, and agreements? What integrations exist today, and which ones need to survive the migration? Is the client's data exportable in standard formats, or is it locked in a proprietary structure? Will the client's team handle data cleaning before handover, or is that on us?

The quality of answers at this stage directly determines whether your estimate is a credible commitment or a number you'll spend the next six months apologizing for.

One pattern I see repeatedly: the cost estimate gets finalized before the complexity is understood. Simple migrations and complex ones look identical on a one-page proposal. They are not identical in execution. A migration involving custom workflows, multi-module field mapping, report development, and third-party integrations is a fundamentally different project than a straightforward data lift-and-shift. Pricing them the same way is how projects go over budget before the first workshop.

**But scoping questions only give you half the picture.**

The questions above tell you what the source system contains. They don't tell you what users actually need. That gap is where migrations quietly fail, and it's exactly the gap I described in my previous post on <a href="#measuring-the-wrong-thing" style="font-weight:700;text-decoration:underline">measuring the wrong thing</a>.

After the internal scoping alignment, the next step is going to the users themselves. Conduct short, focused interviews with each user group. Understand their daily operations. Ask what they actually use in the current system, what they've been working around for years, and what they wish existed but never did. If possible, provide a short trial in a controlled environment, a sandbox configured with realistic data, and collect structured feedback.

This is the step that transforms a migration from a data transfer exercise into an adoption architecture project. Because once you've heard users describe how they actually work, you can build realistic use cases that reflect what the destination system needs to deliver on day one. Not feature parity with the old system. Not a wish list from a requirements spreadsheet. A grounded, validated picture of what "useful" looks like for the people who will decide whether this migration succeeds or fails.

Those use cases become the backbone of every decision downstream: what to configure, what to map, what to skip, and what gaps to flag honestly.

Without this step, you're scoping a migration based on the system. With it, you're scoping a migration based on the work.

### **Phase 1: Initiation and planning, the phase everyone rushes through.**

Once the contract is signed and the project is handed over to the implementation project manager, there's an instinct to jump straight into workshops. Resist it.

Phase 1 is where you build five outputs that will save the project later:

**A scope statement detailed enough to prevent ambiguity.** Not a paragraph in a contract, but a document that specifies exactly which modules are in scope, which data objects will be migrated, what custom development is included, and critically, what is explicitly out of scope. The scope statement should include assumptions and constraints, because the moment a client says "I assumed that was included," and you don't have a document that says otherwise, you've lost the argument.

**A project timeline with a visible critical path.** Weekly-level detail. Clear indication of which work requires client involvement, which is internal, and which is collaborative. A meeting plan with agendas and expected outputs for every workshop. Clients don't just need to know *when* things happen. They need to know *what they're expected to bring* to each session.

**A risk register that's actually maintained.** Not a one-time document created at kickoff and never opened again. Two versions: one shared with the client, one internal with a more exhaustive list. This should be reviewed weekly, with probability, impact, mitigation plans, and contingency actions. In my experience, the projects that get into trouble are never the ones that encountered unexpected risks. They're the ones that identified risks early and then stopped tracking them.

**A budget control tracker that compares estimated days against actual days spent.** Updated weekly. Shared with stakeholders monthly. The moment you see days consumed exceeding the pace of work completed, you need to surface it. If extra service days become necessary, the account manager needs advance notice to manage the commercial conversation, not a surprise at project closure.

**A requirement list and a change log.** Requirements evolve. Scope changes happen. The question is whether those changes are tracked and priced, or whether they accumulate silently until the project is underwater.

The project kickoff itself should align both teams on roles, responsibilities, and resource availability. This is where you make explicit what the client's team needs to contribute, when, and how much effort is involved. Migrations fail when the client assumes it's a turnkey service and the vendor assumes the client will be actively engaged. Kickoff is where you close that gap.

### **Phase 2: Requirements collection, where the real design happens.**

This phase is the heart of the project, and it's where most of the intellectual work lives. It has three distinct workstreams, and they need to run in coordination.

**Application configuration and field mapping.** This is the translation layer between what users had in the old system and what they'll have in the new one. Start by creating an exhaustive list of every data field in the source system. Then assess actual usage, not theoretical usage, actual usage. Run analytics. How many records use each field? A field with 1% usage might not need to migrate at all.

From there, build a configuration and mapping tracker with recommendations. Host a series of workshops with the client to walk through it. Set homework between sessions. Clients need time to review recommendations, consult their teams, and come back with decisions. Once finalized, configure a sandbox environment reflecting the agreed mapping, walk the client through it, and get sign-off before moving forward.

One lesson I've learned the hard way: workshop planning matters as much as workshop content. Share the agenda in advance. Specify what input you need from the client before the session. Define the expected output of each session. Workshops without structure produce conversations without decisions.

**Reports and dashboard development.** If the project includes reporting or analytics, and most enterprise migrations do, this workstream needs its own requirements process. What's the purpose of each report: analysis, internal reporting, or an exportable deliverable? Who's the audience? What's the frequency of use? Which data fields feed into it, and are those fields already mapped correctly?

The trap here is treating reports as a bolt-on. Report requirements should be collected in parallel with field mapping, because the two are interdependent. A report that depends on a field that wasn't migrated is a report that doesn't work on day one.

But here's the thing most implementation teams underestimate: **reports and dashboards are where the migration becomes real for users**. All the work upstream, the data correction, the field mapping, the careful configuration, it's invisible to most end users. They don't see clean data. They see a dashboard that loads instantly with the numbers they need, or they don't. They see a report they can pull in two clicks instead of a manual export that used to take an hour, or they don't.

This is the adoption lever. This is where users go from "the new system works" to "the new system is better." If you want users to stick, this is the workstream to invest in. Not as an afterthought at the end of the project, but as a first-class deliverable scoped with the same rigor as the data migration itself.

When reports and dashboards are done right, they become the daily proof that the migration was worth it. When they're done poorly or skipped entirely, users default to the same Excel workarounds they had before, and you've migrated data into a system that nobody opens.

**Data correction.** This is the work that nobody wants to do and everybody needs. Review the client's data against the destination system's validation standards. Identify duplicates, inconsistencies, fields that exceed character limits, contacts without linked companies, records with missing mandatory fields.

Two rules I enforce on every project: first, data correction decisions belong to the client. It's their data. Don't correct records without permission. Second, share the data correction checklist with the client only after you've run the analysis and prepared results with proposed solutions. Asking clients to review raw checklists multiple times is how you exhaust their patience before the project is halfway done.

### **Phase 3: Data migration, the phase that looks simple and isn't.**

Data migration has two environments and two cycles. Testing first, production second. Each cycle has the same two steps: migrate, then validate.

**Testing environment.** Migrate data in batches. Validate the migration result against the mapping tracker. This is where you catch field mapping errors, broken relationships, workflow misconfigurations, and data that looked clean in a spreadsheet but breaks in the destination system. Every issue found here is an issue that doesn't appear in production.

**Production environment.** Same process, but now it counts. Migrate, validate, confirm with the client. The production migration should feel boring if the testing cycle was thorough.

A tactical note on workflows: when migrating records that involve workflow stages, migrate all records to an initial stage first without assigning a workflow. Then update the workflow stage in a separate step. This avoids triggering automated workflow actions during migration, actions that can create duplicate notifications, incorrect status updates, or data corruption in the destination system.

**Data validation: the step that proves you got it right.**

Migration without validation is a liability. You've moved data from one system to another, but can you prove it arrived intact?

Data validation is the mechanism that answers that question, and it needs to be systematic, not anecdotal. Spot-checking ten records manually is not validation. It's hope.

A proper validation framework operates at three levels. First, count validation: does the number of records in the destination match the number of records in the source, for every object type? Accounts, contacts, opportunities, agreements. If the count doesn't match, something was lost or duplicated, and you need to find it before anyone logs in.

Second, field-level validation: for a statistically significant sample of records, do the field values in the destination match the source? This catches silent mapping errors, truncated text fields, date format conversions gone wrong, and list values that didn't translate correctly. Automate this comparison wherever possible. Manual field-by-field checking doesn't scale, and it misses patterns that a script would catch immediately.

Third, relational validation: are the relationships between records intact? A contact linked to the wrong company. An agreement orphaned from its parent opportunity. A task that lost its link to the record it belonged to. Relational integrity is the hardest thing to validate and the most damaging thing to get wrong, because users will discover broken links one at a time, over weeks, and each discovery erodes trust in the system.

Document the validation results. Share them with the client. Make the evidence visible. A validated migration gives users confidence that the data they're looking at is real. An unvalidated migration gives them a reason to keep their old spreadsheets open, just in case.

### **Phase 4: Project closure, the phase that's not the finish line.**

Training, go-live, and legacy system decommissioning.

Training should target power users first, then the broader team. The implementation project manager conducts the training, not because they're the best trainer, but because this is the last opportunity to walk through the configured environment with the customer success manager present, ensuring a clean handover.

After go-live, there's a monitoring period before the legacy system gets terminated. The project manager confirms with the customer success manager that all users have successfully transitioned. Only then does the legacy tenant get shut down.

This is the handover point: from project to relationship. The customer success manager takes over. The quality of what they inherit, clean data, proper configuration, trained users, documented requirements, determines whether this account grows or churns.

### **What this framework actually protects.**

Every phase, every output, every milestone in this structure exists for one reason: to prevent the kind of failure that doesn't show up in a project status report.

The scope statement prevents scope creep. The risk register prevents surprise. The budget tracker prevents financial blindsides. The requirements workshops prevent building the wrong thing. The data correction process prevents garbage-in-garbage-out. The testing cycle prevents production disasters. The validation framework prevents invisible data rot. The handover process prevents orphaned accounts.

Strip any of these out and you might still deliver the project on time. But "on time" is not the metric that matters. The metric that matters is whether users adopt the system, whether the client renews, and whether the migration becomes a foundation for growth rather than a source of regret.

A migration framework isn't a bureaucratic exercise. It's an insurance policy against the most expensive kind of project failure, the kind that looks like success until it doesn't.

---

*If the framework described here raises the question of what AI can take over once the process is defined, the next piece, <a href="#you-already-know-how-work-with-AI" style="font-weight:700;text-decoration:underline"><strong><u>You Already Know How to Work with AI</u></strong></a>, walks through how to delegate repeatable steps to AI using the same briefing discipline you already use with people.*
