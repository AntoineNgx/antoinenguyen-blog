# You Already Know How to Work with AI

### Managing AI is just delegation. You've been doing that for years.

---

## The hire you didn't expect to make

Imagine you've just got budget to bring someone new onto your team. They're capable. Well-credentialed. Quick to learn. But they've never worked at your company before, don't know your clients, don't know your processes, and have never touched the tools you use.

You would not hand them a client-facing tasks on day one.

You'd start them on back-office tasks: the structured, repeatable work that sits behind your client-facing output. Compiling a analyzed correction list. Formatting an export for import somewhere else. You'd give them clear instructions, relevant materials, and a specific expected output. You'd check their first few attempts carefully before letting the work flow through.

And eventually, as they proved themselves on the bounded tasks, you'd trust them with more.

That is the mental model for AI. Not a magic oracle. Not a co-pilot with opinions about your strategy. A capable but uninformed assistant who needs the same things any capable but uninformed assistant needs: context, a clear task, and a well-defined output.

The shift that matters is not technical. It is managerial. The question is not "can I use AI?" but "what would I delegate, and how precisely would I brief it?"

---

## What training actually looks like

When you onboard a new team member, you do five things instinctively. You tell them who they are in this context. You give them the background materials they need to not operate in the dark. You set a goal so they know what success looks like. You give them a specific task to start on. And you tell them what you expect back.

Working with AI, those five things have exact equivalents. The role is a sentence in the system prompt. The materials are the documents you paste into context. The goal is part of the instructions. The task is what you type. The expected output is how you end the prompt.

One way to see this clearly:

<style>
  .sr-only{position:absolute;width:1px;height:1px;padding:0;margin:-1px;overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;border:0}
  .cmp{padding:1rem 0;width:100%}
  .cmp-header{display:grid;grid-template-columns:1fr 1fr 1fr;gap:0;margin-bottom:0}
  .col-label{padding:9px 14px;font-size:11px;font-weight:500;letter-spacing:.04em;color:var(--color-text-tertiary);text-transform:uppercase}
  .col-label.center{text-align:center}
  .cmp-body{border:0.5px solid var(--color-border-tertiary);border-radius:var(--border-radius-lg);overflow:hidden}
  .row{display:grid;grid-template-columns:1fr 1fr 1fr;gap:0;border-bottom:0.5px solid var(--color-border-tertiary)}
  .row:last-child{border-bottom:none}
  .cell{padding:11px 14px;font-size:13px;color:var(--color-text-primary);line-height:1.5}
  .cell.concept{color:var(--color-text-secondary);font-size:12px;font-weight:500;background:var(--color-background-secondary);display:flex;align-items:center}
  .cell.human{background:var(--color-background-primary)}
  .cell.ai{background:var(--color-background-primary)}
  .divider{width:0.5px;background:var(--color-border-tertiary)}
</style>
<h2 class="sr-only">Comparison of what you give a new human hire versus what you give Claude — showing the same five elements in each case</h2>
<div class="cmp">
  <div class="cmp-header">
    <div class="col-label">Element</div>
    <div class="col-label">New hire on day one</div>
    <div class="col-label">Claude</div>
  </div>
  <div class="cmp-body">
    <div class="row">
      <div class="cell concept">What they are</div>
      <div class="cell human">A capable person who doesn't know your context yet</div>
      <div class="cell ai">A capable model that doesn't know your context yet</div>
    </div>
    <div class="row">
      <div class="cell concept">Role</div>
      <div class="cell human">"You're a data analyst on the migration team"</div>
      <div class="cell ai">Same sentence, in the system prompt</div>
    </div>
    <div class="row">
      <div class="cell concept">Background materials</div>
      <div class="cell human">The project brief, the field mapping doc, past examples</div>
      <div class="cell ai">The same documents, pasted into context</div>
    </div>
    <div class="row">
      <div class="cell concept">The task</div>
      <div class="cell human">"Parse this error log and flag anything that blocks record creation"</div>
      <div class="cell ai">Same sentence, as the user message</div>
    </div>
    <div class="row">
      <div class="cell concept">Expected output</div>
      <div class="cell human">"Give me a table: error type, affected records, suggested fix"</div>
      <div class="cell ai">Same sentence, in the prompt</div>
    </div>
  </div>
</div>

The parallel is not a metaphor stretched thin for effect. It is structurally accurate. The brief you would write for a junior analyst on their first day is, with minor translation, the prompt you write for AI. The discipline of prompt writing is the discipline of clear delegation. If you have managed people, you already know how to do this.

The translation your notes lay out directly: train a skill equals skill, materials equal project document, give instruction equals prompt. Role, context, goal, task, expected output. It is the same framework you would use in a handover email.

---

## The worked example — one step, written as a brief

In a recent data migration project, one of the crucial work is moving client records from one CRM platform to another. There is a step that runs repeatedly throughout the process. Every time the migration tool runs, it produces a log. That log contains successes, warnings, and errors. Someone has to read it, classify what kind of problem each error represents, and decide what happens next.

On a complex migration, that log can contain hundreds of entries. The classification itself is not complicated. But it is time-consuming, pattern-dependent, and almost entirely mechanical. It is exactly the kind of back-office task you would hand to a capable assistant on day one.

Here is what the task brief looks like, written in plain language:

---

> **To:** Migration assistant
> **Re:** Step 2.8 — Parse migration log and recommend next steps
>
> **Your role:** You are a data migration analyst working on a CRM migration project. You have no client-facing responsibilities at this stage. Your job is to process internal logs and prepare recommendations for the project team.
>
> **Background:** We are migrating records from the source Excel spreadsheet to the destination CRM using a migration tool. After every run on the migration tool, we download a log file. That log contains three types of entries: successes (record created correctly), warnings (record created but with missing or incomplete fields), and errors (record not created).
>
> **Goal:** Classify every error and warning in the log, and for each one, recommend the correct next step according to the routing rules below.
>
> **Task:** You will receive a log file. For each error or warning entry, identify: the affected record ID, the error type, and which routing rule applies.
>
> Routing rules:
> — If the error blocks record creation entirely, classify as "blocking" and recommend: fix in the Excel spreadsheet, re-run dry run.
> — If the record was created but fields are missing, classify as "missing info" and recommend: generate the import file to import data via the migration tool.
> — If the error cannot be classified with confidence, classify as "ambiguous" and flag for human review. Do not route ambiguous cases automatically.
>
> **Expected output:** A table with five columns: Record ID, Object type, Error message (shortened), Classification, Recommended action. One row per error or warning entry. No prose, no commentary. Ambiguous cases should appear in the table with classification "ambiguous" and action "human review required."

---

That brief took less than fifteen minutes to write. The task it describes, run manually, takes the better part of an afternoon on a busy migration. Run through an AI model on a well-structured log file, it takes under a minute. The only intellectual work was knowing the process well enough to write it down precisely (I use Claude cause this instruction and skills can be built in with its Project and Skill to reuse).

---

## Break it down, and break it down again

The most common objection at this point is not about technology. It is about complexity.

"My work isn't like that. Every situation is different. I can't script out a process that runs case by case."

That objection deserves a direct answer: you are right, and that is exactly where to look.

"Case by case" is not a reason to stop. It is an instruction to decompose further. When you face a cases, in your brain, you cross-referenced similar cases you know and how did they got solved. It's the same here. You just need to name the cases, you can describe what happens in each one. If you can describe what happens in each one, you have the routing logic. And routing logic is something you can delegate.

The migration example above is itself a product of this decomposition. The original version of that task was "handle the errors." Handled how? Depends on the error. Which errors? All of them. Then what? Depends.

That version is undelegatable. Not because the task is too complex, but because the thinking hasn't been done yet.

The question that unlocks it is always the same: what are the cases, when does each one happen, and what do you do when it does? Force yourself to list the cases. You will find there are usually two or three, occasionally four. Each one has a trigger condition and a defined response. That structure is the brief.

<style>
  .sr-only{position:absolute;width:1px;height:1px;padding:0;margin:-1px;overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;border:0}
  .dcmp{padding:1rem 0;font-size:13px}
  .vague-box{padding:10px 16px;border:0.5px solid var(--color-border-secondary);border-radius:var(--border-radius-md);background:var(--color-background-secondary);color:var(--color-text-secondary);text-align:center;margin:0 auto 6px;max-width:320px;line-height:1.5}
  .vague-label{font-size:11px;color:var(--color-text-tertiary);text-align:center;margin-bottom:14px}
  .arrow-down{text-align:center;color:var(--color-text-tertiary);font-size:13px;margin:2px 0 6px}
  .q-box{padding:10px 16px;border:0.5px solid var(--color-border-secondary);border-radius:var(--border-radius-md);background:var(--color-background-primary);color:var(--color-text-primary);font-weight:500;text-align:center;margin:0 auto 4px;max-width:320px}
  .branches{display:grid;grid-template-columns:1fr 1fr 1fr;gap:10px;margin-top:14px}
  .branch{border-radius:var(--border-radius-md);overflow:hidden;border:0.5px solid var(--color-border-tertiary)}
  .branch-hdr{padding:8px 10px;font-size:11px;font-weight:500}
  .b1-hdr{background:#EEEDFE;color:#26215C}
  .b2-hdr{background:#E1F5EE;color:#04342C}
  .b3-hdr{background:#FAECE7;color:#4A1B0C}
  @media(prefers-color-scheme:dark){
    .b1-hdr{background:#26215C;color:#CECBF6}
    .b2-hdr{background:#04342C;color:#9FE1CB}
    .b3-hdr{background:#4A1B0C;color:#F5C4B3}
  }
  .branch-body{padding:8px 10px;background:var(--color-background-secondary)}
  .condition{font-size:11px;color:var(--color-text-tertiary);margin-bottom:5px;line-height:1.4}
  .action{font-size:12px;color:var(--color-text-primary);line-height:1.5}
  .feasibility{margin-top:6px;display:inline-block;font-size:10px;padding:2px 6px;border-radius:10px;font-weight:500}
  .f-ai{background:#EEEDFE;color:#534AB7}
  .f-human{background:#D3D1C7;color:#444441}
  @media(prefers-color-scheme:dark){
    .f-ai{background:#26215C;color:#AFA9EC}
    .f-human{background:#2C2C2A;color:#B4B2A9}
  }
  .connector-row{display:flex;align-items:flex-start;justify-content:center;gap:0;margin-bottom:2px;position:relative;height:24px}
  .v-line{width:0.5px;height:24px;background:var(--color-border-secondary);margin:0 auto}
  .h-spread{position:absolute;top:0;left:16.5%;right:16.5%;height:0.5px;background:var(--color-border-secondary)}
  .tick-left{position:absolute;left:16.5%;top:0;width:0.5px;height:12px;background:var(--color-border-secondary)}
  .tick-mid{position:absolute;left:50%;top:0;width:0.5px;height:12px;background:var(--color-border-secondary);transform:translateX(-50%)}
  .tick-right{position:absolute;right:16.5%;top:0;width:0.5px;height:12px;background:var(--color-border-secondary)}
</style>
<h2 class="sr-only">Diagram showing how a vague "case by case" task decomposes into three named cases, each with a condition and defined action</h2>
<div class="dcmp">
  <div class="vague-box">"It depends — every error is different. I handle it case by case."</div>
  <div class="vague-label">Before decomposition: opaque, undelegatable</div>
  <div class="arrow-down">↓ ask: what are the cases?</div>
  <div class="q-box">When you get an error in the migration log, what decides what you do next?</div>
  <div style="position:relative;height:28px;margin-top:2px">
    <div class="h-spread"></div>
    <div class="tick-left"></div>
    <div class="tick-mid"></div>
    <div class="tick-right"></div>
  </div>
  <div class="branches">
    <div class="branch">
      <div class="branch-hdr b1-hdr">Case 1: blocking error</div>
      <div class="branch-body">
        <div class="condition">When: the record cannot be created at all</div>
        <div class="action">Fix the source data in Classic, re-run the dry run</div>
        <span class="feasibility f-ai">LLM</span>
      </div>
    </div>
    <div class="branch">
      <div class="branch-hdr b2-hdr">Case 2: missing info</div>
      <div class="branch-body">
        <div class="condition">When: the record was created but fields are incomplete</div>
        <div class="action">Generate a Bane import Excel, run the supplementary import</div>
        <span class="feasibility f-ai">LLM</span>
      </div>
    </div>
    <div class="branch">
      <div class="branch-hdr b3-hdr">Case 3: ambiguous</div>
      <div class="branch-body">
        <div class="condition">When: error type cannot be classified with confidence</div>
        <div class="action">Flag for human review before any action is taken</div>
        <span class="feasibility f-human">Human</span>
      </div>
    </div>
  </div>
  <div style="margin-top:10px;padding:8px 10px;border-radius:var(--border-radius-md);border:0.5px dashed var(--color-border-secondary);font-size:11px;color:var(--color-text-tertiary);text-align:center;line-height:1.5">
    After decomposition: three named cases, each with a condition, an action, and a clear owner. Two of three are delegatable to AI today.
  </div>
</div>

One more thing worth saying about this: you do not need to automate every branch. In the example above, the ambiguous case stays with a human. That is intentional. The AI handles the two high-volume, well-defined branches. The human handles the exception. That division is not a failure of automation. It is the correct design.

The goal is not full automation. It is delegating the right parts.

---

## Before you build anything — the feasibility question

Before writing a single prompt, it is worth asking a small set of questions. Not to build a business case. Not to run a pilot program. Just to check whether the task in front of you is actually ready to delegate.

The questions are not technical. They are the same questions a good manager asks before handing work to anyone:

Can I describe this task clearly enough that someone who has never seen it could do it? Is the output specific enough that I'd know a good result from a bad one? Does the input live somewhere accessible, or is it locked in a system with no export? If the output is wrong, can I catch that before it reaches a client or a production system? And: is this task recurring enough that the time I spend writing the brief will be paid back within a few runs?

Five questions. Work through them honestly for the task in front of you:

<style>
  .sr-only{position:absolute;width:1px;height:1px;padding:0;margin:-1px;overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;border:0}
  .fcheck{padding:1rem 0;max-width:560px}
  .q-item{display:flex;align-items:flex-start;gap:10px;padding:10px 0;border-bottom:0.5px solid var(--color-border-tertiary);cursor:pointer}
  .q-item:last-of-type{border-bottom:none}
  .q-toggle{width:18px;height:18px;border-radius:4px;border:0.5px solid var(--color-border-secondary);background:var(--color-background-secondary);flex-shrink:0;margin-top:1px;display:flex;align-items:center;justify-content:center;transition:background .15s,border-color .15s}
  .q-toggle.checked{background:#1D9E75;border-color:#1D9E75}
  .q-toggle svg{display:none}
  .q-toggle.checked svg{display:block}
  .q-text{font-size:13px;color:var(--color-text-primary);line-height:1.5}
  .q-sub{font-size:11px;color:var(--color-text-tertiary);margin-top:2px;line-height:1.4}
  .result-bar{margin-top:14px;padding:12px 14px;border-radius:var(--border-radius-md);border:0.5px solid var(--color-border-tertiary);background:var(--color-background-secondary);transition:background .3s}
  .result-label{font-size:12px;font-weight:500;color:var(--color-text-primary);margin-bottom:4px}
  .result-verdict{font-size:13px;color:var(--color-text-secondary);line-height:1.5}
  .score-track{height:4px;border-radius:2px;background:var(--color-border-tertiary);margin:10px 0 0;overflow:hidden}
  .score-fill{height:100%;border-radius:2px;transition:width .35s,background .35s}
</style>
<h2 class="sr-only">Interactive checklist to assess whether a task is ready to delegate to AI, with a score and verdict that updates as you check items</h2>
<div class="fcheck" id="fc">
  <div class="q-item" onclick="toggle(0)">
    <div class="q-toggle" id="t0"><svg width="10" height="8" viewBox="0 0 10 8" fill="none"><path d="M1 4l2.5 2.5L9 1" stroke="#fff" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
    <div><div class="q-text">Can you describe the task clearly enough to brief a new assistant?</div><div class="q-sub">If you'd struggle to explain it, the AI will struggle to do it.</div></div>
  </div>
  <div class="q-item" onclick="toggle(1)">
    <div class="q-toggle" id="t1"><svg width="10" height="8" viewBox="0 0 10 8" fill="none"><path d="M1 4l2.5 2.5L9 1" stroke="#fff" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
    <div><div class="q-text">Is the output format specific enough that you'd know a good result from a bad one?</div><div class="q-sub">Vague outputs produce vague results. Define what done looks like.</div></div>
  </div>
  <div class="q-item" onclick="toggle(2)">
    <div class="q-toggle" id="t2"><svg width="10" height="8" viewBox="0 0 10 8" fill="none"><path d="M1 4l2.5 2.5L9 1" stroke="#fff" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
    <div><div class="q-text">Does the task run on text, files, or structured data the AI can read?</div><div class="q-sub">AI works on what it can see. If the input lives in a system with no export, that's a prerequisite to solve first.</div></div>
  </div>
  <div class="q-item" onclick="toggle(3)">
    <div class="q-toggle" id="t3"><svg width="10" height="8" viewBox="0 0 10 8" fill="none"><path d="M1 4l2.5 2.5L9 1" stroke="#fff" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
    <div><div class="q-text">Is a wrong output recoverable before it reaches a client or a production system?</div><div class="q-sub">Low-stakes errors are a feature, not a bug — they're how you learn. Irreversible ones need a human checkpoint first.</div></div>
  </div>
  <div class="q-item" onclick="toggle(4)">
    <div class="q-toggle" id="t4"><svg width="10" height="8" viewBox="0 0 10 8" fill="none"><path d="M1 4l2.5 2.5L9 1" stroke="#fff" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg></div>
    <div><div class="q-text">Is this task repeatable? Will you run it more than a handful of times?</div><div class="q-sub">One-off tasks rarely justify the brief-writing time. Recurring tasks pay back the investment fast.</div></div>
  </div>
  <div class="result-bar" id="result-bar">
    <div class="result-label" id="result-label">Check the boxes above</div>
    <div class="result-verdict" id="result-verdict">Your readiness score will appear here as you go.</div>
    <div class="score-track"><div class="score-fill" id="score-fill" style="width:0%;background:#D3D1C7"></div></div>
  </div>
</div>
<script>
const states=[false,false,false,false,false];
const verdicts=[
  ["Not ready yet","Write out what the task is and what a good result looks like. Clarity comes first.","#D3D1C7"],
  ["Early stage","You have a start. Keep defining the output and checking the inputs available to you.","#FAC775"],
  ["Getting there","Half the conditions are met. Identify the remaining gaps before writing your first prompt.","#EF9F27"],
  ["Nearly ready","One step from delegatable. Resolve the remaining condition and try a pilot.","#1D9E75"],
  ["Nearly ready","One step from delegatable. Resolve the remaining condition and try a pilot.","#1D9E75"],
  ["Ready to delegate","Write the brief, run a pilot on a low-stakes batch, review the output, and iterate.","#0F6E56"]
];
function toggle(i){
  states[i]=!states[i];
  const t=document.getElementById('t'+i);
  t.classList.toggle('checked',states[i]);
  update();
}
function update(){
  const n=states.filter(Boolean).length;
  const pct=n*20;
  const sf=document.getElementById('score-fill');
  sf.style.width=pct+'%';
  sf.style.background=verdicts[n][2];
  document.getElementById('result-label').textContent=n+'/5 — '+verdicts[n][0];
  document.getElementById('result-verdict').textContent=verdicts[n][1];
}
</script>

The checklist is not a gate. It is a diagnostic. If you answer no to the first two questions, the work is not on the AI. It is on you, getting clear enough about the task to brief it. That clarity is useful regardless of whether AI ends up doing the work.

The migration feasibility analysis behind this project identified 21 discrete steps across three phases. Twelve were fully automatable. Six required AI plus human supervision. Three had to stay human: the decisions that belong to the client, the go/no-go before a destructive operation runs on production data, and the field mapping choices that require business judgment. Those three were identified not by gut feel, but by asking exactly this set of questions for each step.

---

## Where to start

The point of all of this is not to build an agentic system. It is to find one back-office task this week, write a brief for it, and try it.

Not the most complex task. Not the one with the biggest upside. The one you find yourself doing repetitively, on structured inputs, where a wrong output is recoverable. The one where you already know the cases, even if you've never written them down.

Write the brief as if you were handing it to a capable person on their first day. Role, context, goal, task, expected output. Paste in the relevant documents. Run it. Review the output carefully the first few times, the same way you would with a new hire. Adjust the brief where the output surprises you.

That is the full process. The technology is not the hard part. The hard part is the thinking that good delegation has always required: being specific enough, being honest about what can be defined and what cannot, and being willing to stay in the loop where the stakes require it.

If you've managed people, you already have that skill. You're just applying it somewhere new.

---

*This post is part of a series on how AI fits into SaaS implementation and data migration work. If you want to understand the project structure that sits around the kind of work described here, the previous piece, <a href="#the-migration-that-actually-sticks" style="font-weight:700;text-decoration:underline"><strong><u>The SaaS Implementation That Actually Sticks</u></strong></a>, goes into the phases, milestones, and decisions that separate migrations that hold from migrations that quietly collapse.*
