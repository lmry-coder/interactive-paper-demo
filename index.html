<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>The Interactive Paper · Shillingsburg &amp; Valentino 2011</title>
  <meta name="description" content="An interactive reading layer on a scholarly article. Demo." />

  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400;0,500;0,600;0,700;1,400&family=Raleway:wght@300;400;500;600;700&display=swap" rel="stylesheet" />

  <script crossorigin src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
  <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
  <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>

  <style>
    * { box-sizing: border-box; }
    html, body { margin: 0; padding: 0; background: #F5F2EC; }
    body { font-family: 'Lora', Georgia, serif; color: #1A2B3C; }

    .paper-body p { margin: 0 0 1.1em 0; line-height: 1.75; }
    .paper-body h3 {
      font-family: 'Raleway', sans-serif;
      font-weight: 600;
      font-size: 0.72rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: #1A2B3C;
      margin: 2.4em 0 1em 0;
      padding-bottom: 0.4em;
      border-bottom: 1px solid #D4C9B5;
    }

    .chat-scroll::-webkit-scrollbar { width: 6px; }
    .chat-scroll::-webkit-scrollbar-track { background: transparent; }
    .chat-scroll::-webkit-scrollbar-thumb { background: #D4C9B5; border-radius: 3px; }

    .mode-btn, .profile-btn, .seed-btn {
      font-family: 'Raleway', sans-serif;
      transition: all 0.15s ease;
      cursor: pointer;
    }

    .mode-btn:hover, .profile-btn:hover { background: #EBE6DB !important; }
    .seed-btn:hover { background: #1A2B3C !important; color: #F5F2EC !important; }

    .send-btn:hover:not(:disabled) { background: #0A4D5C !important; }
    .send-btn:disabled { opacity: 0.4; cursor: not-allowed; }

    .epistemic-supported { color: #0A4D5C; font-weight: 600; }
    .epistemic-inference { color: #8B6914; font-weight: 600; }
    .epistemic-notstated { color: #7A2E2E; font-weight: 600; }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(4px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .msg { animation: fadeIn 0.25s ease; }

    .pulse {
      display: inline-block;
      width: 6px; height: 6px;
      background: #0A4D5C;
      border-radius: 50%;
      animation: pulse 1.4s infinite;
      margin-right: 4px;
    }
    .pulse:nth-child(2) { animation-delay: 0.2s; }
    .pulse:nth-child(3) { animation-delay: 0.4s; }
    @keyframes pulse {
      0%, 60%, 100% { opacity: 0.3; }
      30% { opacity: 1; }
    }

    @media (max-width: 900px) {
      .split { grid-template-columns: 1fr !important; }
      .paper-pane { border-right: none !important; border-bottom: 1px solid #D4C9B5; max-height: 50vh; }
    }

    .spin { animation: spin 1s linear infinite; }
    @keyframes spin { to { transform: rotate(360deg); } }
  </style>
</head>
<body>
  <div id="root"></div>

  <script type="text/babel" data-type="module">
    const { useState, useRef, useEffect } = React;

    // ============================================================
    // PAPER CONTENT
    // ============================================================

    const PAPER = {
      title: 'Teaching a Child With Autism to Mand for Information Using "How"',
      authors: 'M. Alice Shillingsburg & Amber L. Valentino',
      affiliation: 'Marcus Autism Center and Emory University School of Medicine',
      journal: 'The Analysis of Verbal Behavior',
      year: '2011',
      volume: '27',
      pages: '179–184',
      abstract: `Children with autism often do not learn to mand for information without structured teaching. Studies have demonstrated that manipulation of establishing operations (EOs), prompts, prompt fading, and differential reinforcement are effective in teaching children with autism to ask "wh" questions such as "what," "who," and "where." To date, no studies have evaluated procedures to teach children with autism to mand for information using "how." Teaching the mand, "how" is uniquely challenging because once the information regarding how to do something is provided, the EO may no longer be present. The following study evaluated a procedure to teach one child with autism to mand for information using "how" to obtain information to complete multiple activities. The results have implications for clinical application and future research on contriving EOs to teach the mand, "how."`,
      keywords: 'autism, establishing operations, generalization, language acquisition, mands, question asking',
      sections: {
        introduction: `Typically developing children engage in frequent question asking (Brown, 1968). When question asking is under the control of an establishing operation (EO) and the behavior results in information that is specific to the EO, these questions may be functionally classified as mands for information (Michael, 1988). Unfortunately, many children with autism do not learn to mand for information without structured teaching (Charlop & Milstein, 1989; Endicott & Higbee, 2007).

Early studies established that question asking could be taught to individuals with disabilities using prompting, fading, chaining, differential reinforcement (Bondy & Erickson, 1976; Hung, 1977; Twardosz & Baer, 1973), and videotaped rehearsal and feedback (Knapczyk, 1989). Sundberg, Loeb, Hale, and Eigenheer (2002) noted that earlier studies may have neglected the role of the EO by teaching when an EO was not present and/or by using contrived reinforcers (e.g., tokens) rather than functional reinforcers (e.g., information). Unfortunately, this may result in less functional use of the mand. Several studies have effectively contrived EOs and used functional reinforcers to teach the mands, "what?" (e.g., Williams, Donley, & Keller, 2000), "who?," "where?," (e.g., Endicott & Higbee, 2007; Lechago, Carr, Grow, Love, & Almason, 2010; Sundberg et al., 2002), "which?," and "when?" (e.g., Shillingsburg, Valentino, Bowen, Bradley, & Zavatkay, 2011).

To date, no studies have investigated strategies for teaching children with autism to mand for information using the response form "how." This may be due to the unique challenge of arranging multiple opportunities for teaching while ensuring that an EO controls the response. In other response forms such as "who" and "where," trials can be arranged such that the information provided differs each trial, ensuring the information remains valuable. For example, the mand, "who?" might be taught when a child is told that someone has a preferred toy. The natural reinforcer for the mand would be information about who has her toy. Multiple learning opportunities can be arranged when information about who has the toy differs each trial. In contrast, when a child mands, "how?," and information specific to the request is provided, the information may lose its value because the individual learns to complete the task independently, rendering the information unnecessary. This unique characteristic presents clinical challenges in teaching the mand for information "how." For example, if a therapist contrives a situation in which there is an EO for information, prompts the child to ask "how," and provides the information, there may be no other opportunities using the same scenario to present additional teaching trials. The purpose of the present study was to teach a child with autism to mand for information using "how." To ensure a sufficient number of trials, several scenarios were used to provide multiple opportunities to teach the mand. Additionally, independence with each task was continually assessed to determine if an EO was present.`,
        method: `Participant, Setting, and Materials. Samuel, a 7 year 8-month-old male diagnosed with autism by an independent psychologist participated in the study. Samuel attended a full-day behavioral intervention program for children with language deficits and demonstrated well-developed mand, tact, and intraverbal repertoires. He emitted 3 to 6 word phrases and used prepositions, pronouns, and adjectives correctly. He typically used a variety of "wh" questions to access information (e.g., "what is that?" "when can we go outside?"). Samuel was selected for the study based on a report from his parents and therapists that he did not emit the mand "how" to access information to complete a task or activity. In such situations, he typically persisted with mands for the activity or item and occasionally used the mand "help."

Samuel was taught in a one-on-one format using discrete trial instruction. Trials were conducted in a classroom and/or on the playground twice per week. Materials included typical classroom items (e.g., desks, chairs, shelves, toys) and the items necessary for each activity. Other children and instructors were present but did not interact with Samuel during sessions.

Response Measurement and Interobserver Agreement. Trial-by-trial data were collected on correct independent manding "how?" within 5 s of the therapist contriving the EO. These data were summarized as cumulative independent "how" mands across trials for each activity. A second independent observer collected data during 7.4% of trials. Point-by-point interobserver agreement (IOA) was calculated by dividing the number of agreements by the number of agreements and disagreements and multiplying by 100%. IOA was 100%.

Scenarios. Six "how" scenarios involving highly preferred activities were used: (1) Computer with sound muted, (2) Walkie talkies with talk button not pressed, (3) Swing with gate to playground locked, (4) Computer 2 with monitor unplugged, (5) TV with remote missing batteries, and (6) Snack closet locked. For each scenario, the therapist's response following a correct "how" mand was a specific instruction for completing the task (e.g., "unmute the computer," "plug in the monitor").

Experimental Design. A multiple baseline design across "how" scenarios was used to evaluate the effects of teaching. If the mand "how" emerged in untreated scenarios, treatment was not initiated with those scenarios. The use of multiple scenarios allowed for trials to continue with other scenarios if there was not an EO for information about how to do a task for one scenario. In addition, this arrangement allowed for continual assessment of generalized manding under various conditions.

Experimental Procedure. One trial was conducted for each scenario each day, two days per week. Prior to each trial, an EO for the activity was assessed by asking Samuel if he would like to engage in the activity.

Baseline: Each scenario was presented one trial at a time since one presentation of the information may abolish the EO. Samuel was given 5 s to begin to complete the necessary task independently or mand using "how." If he initiated completing the task, additional time was allowed for him to fully complete the task. If he did not initiate the task, 5 s was given for the response "how." If Samuel emitted an incorrect response or no response within 5 s, no information or reinforcer was provided, and the next trial was initiated.

Mand training: Upon implementation of treatment to a scenario, a trial was conducted with an immediate prompt for the correct response without an opportunity for an independent response. All subsequent trials were presented with an opportunity to respond independently followed by a prompt if necessary. If Samuel emitted no response or an incorrect response during the 5 s delay, the vocal model "how" was provided by the instructor. Once he echoed the response "how," information was provided that led to completion of the task and access to the preferred activity. If he completed the task independently, the trial was terminated and the scenario was no longer presented since the information was no longer necessary. Each scenario in treatment was conducted until 3 consecutive trials resulted in an independent mand "how" or until the participant began to complete the task independently.`,
        results: `Samuel's cumulative independent "how?" mands were tracked across trials during each scenario.

During baseline for the Muted Computer scenario, Samuel did not mand "how?" Upon implementation of mand training, a teaching trial was immediately conducted. On all subsequent days, each trial began with an opportunity to respond independently. Samuel independently emitted the mand "how" after two teaching trials; manding did not occur during any other scenarios. Additional teaching trials for the Muted Computer scenario were not conducted because Samuel learned to unmute the computer and did so independently during the next presented opportunity.

Following implementation of treatment for the Walkie Talkie scenario, Samuel independently manded "how" after four trials (i.e., one initial teaching trial and three trials with opportunities to respond independently). Interestingly, during mand training on the Walkie Talkie scenario, Samuel independently manded "how" in the other four scenarios still in baseline.`,
        discussion: `The current study is the first to evaluate an intervention to teach a child with autism to mand for information using "how." The results obtained suggest that the preparation used facilitated appropriate stimulus control of the mand "how?" by contriving EOs for information, using natural reinforcers (i.e., information), and arranging multiple opportunities for teaching. An EO for information regarding how to complete the task was indicated if Samuel attempted to, but could not complete the task independently, establishing the information on how to complete it as valuable. Future research could take additional steps to ensure EO control by alternating trials in which information is needed with trials in which information is not needed.

While social validity was not formally assessed, manding "how?" would appear to be an important skill for children with autism when they are placed in settings where they are asked to complete unknown tasks. If an instructor is unaware that the child does not know how to complete a task, the child may not complete his or her work and this lack of work completion may result in negative consequences. However, if a child can effectively mand "how," he or she can then obtain information in order to effectively complete the task.`,
        limitations: `There are several limitations to the current study that warrant discussion.

First, because only one participant was included, replication of these procedures with other participants is needed. Samuel had a history of emitting the mand "how" in two contrived settings. While this skill had not been observed in natural settings, it is unknown whether similar results would be obtained with participants without a mand for information repertoire in general or with some mands for information but no history of manding "how."

Second, the mand targeted was the response "how?" as opposed to a more specific response such as "how do I unmute the computer?" The general response form "how?" was selected because it was deemed simpler for Samuel to learn. However, this response may not be as functional as more specific mands in other situations.

Third, there was a lack of assessment of treatment integrity, maintenance, and social validity. Given the importance of the EO and its complexity specific to the mand "how," a measure of treatment fidelity would allow for assurance that each scenario was contrived appropriately.

Fourth, the percentage of trials with IOA (7.4%) is lower than is typically reported in single subject design. According to Kazdin (1982) if checks on agreement show observers agree almost all of the time, agreement may not need to be checked frequently.

Fifth, the present study did not include procedures to promote generalization other than teaching in multiple scenarios. Other ways to promote generalization might include training with multiple instructors and with multiple exemplars of each scenario.

Finally, the generalization observed across baselines limits the experimental design employed in the current study. Following the implementation of treatment with the second scenario, increases in the remaining baselines were also observed. Although this is an ideal clinical outcome, it limits the utility of the multiple baseline design in assessing the effectiveness of the current teaching procedures.`,
      },
    };

    // ============================================================
    // PROMPT ARCHITECTURE
    // ============================================================

    const SYSTEM_PROMPT = `You are a scholarly reading interface for a specific research article. Your purpose is to help readers access, interpret, and engage with this paper faithfully and usefully.

You must:
- prioritize fidelity to the article above all else
- distinguish clearly between what the paper directly states, what is a reasonable inference, and what is not stated or uncertain
- never fabricate findings, methods, citations, or claims
- answer only from the provided article content unless explicitly told otherwise
- point to specific sections (Abstract, Introduction, Method, Results, Discussion, Limitations) when citing
- adapt your explanation to the reader's stated role and goal
- if the paper does not answer a question, say so plainly

You are not a general chatbot. You are a transparent reading layer on a single article. Do not invent content the paper does not contain. Do not pad answers. When you label a statement as "Supported by the paper," it must be grounded in the text provided.

For analytical or evaluative responses, label major points as one of:
- Supported by the paper
- Inference from the paper
- Not stated in the paper

Keep responses focused. Avoid marketing language and avoid hedging past the point of usefulness.`;

    const ARTICLE_CONTEXT = `ARTICLE:
Title: ${PAPER.title}
Authors: ${PAPER.authors}
Journal: ${PAPER.journal}, ${PAPER.year}, ${PAPER.volume}, ${PAPER.pages}
Keywords: ${PAPER.keywords}

ABSTRACT:
${PAPER.abstract}

INTRODUCTION:
${PAPER.sections.introduction}

METHOD:
${PAPER.sections.method}

RESULTS:
${PAPER.sections.results}

DISCUSSION:
${PAPER.sections.discussion}

LIMITATIONS (extracted from Discussion):
${PAPER.sections.limitations}`;

    const READER_PROFILES = {
      editor: { label: 'Journal editor', description: 'Evaluating whether the article is suitable for publication or promotion', tone: 'executive, crisp, oriented toward editorial value and contribution' },
      clinician: { label: 'Practicing clinician', description: 'SLP, BCBA, or therapist deciding whether this changes practice', tone: 'practical, translational, focused on clinical application' },
      researcher: { label: 'Researcher', description: 'Evaluating methodological rigor and theoretical contribution', tone: 'technical, precise, methodologically careful' },
      student: { label: 'Graduate student', description: 'Learning the concepts and situating the paper in a literature', tone: 'plainspoken, scaffolded, willing to define jargon' },
      family: { label: 'Family member or caregiver', description: 'Trying to understand what this means for a child in their life', tone: 'accessible, warm, free of unnecessary jargon' },
    };

    const MODES = {
      summary: {
        label: 'Faithful summary',
        description: 'A compact, honest account of what the paper does',
        instruction: `Respond with a faithful summary. Include:
- one-sentence thesis
- three key contributions
- what kind of evidence the paper uses
- one important limitation
Keep it under 180 words. Do not editorialize.`,
      },
      claims: {
        label: 'Claim / evidence / uncertainty',
        description: 'What the paper claims, what supports it, and what it does not establish',
        instruction: `Organize the response under these headings, in this order:
- Main claim
- Evidence presented
- Assumptions or uncertainties
- What the paper does not establish
Be specific. Cite sections (Method, Results, Discussion) where relevant.`,
      },
      translation: {
        label: 'Reader-specific translation',
        description: 'The paper explained for this reader',
        instruction: `Explain this paper for the reader profile specified. Include:
- why it matters to this reader specifically
- any jargon that needs translation (define it)
- one possible misuse or overreading of the findings this reader should avoid
Adapt tone to the reader.`,
      },
      appraisal: {
        label: 'Critical appraisal',
        description: 'A rigorous evaluation using only what is in the paper',
        instruction: `Evaluate the paper using only the content provided. Address:
- clarity of research question
- appropriateness of methods as described
- strength of evidence relative to the claims made
- limitations the authors acknowledge
- limitations that remain after what the authors acknowledge
Do not overstate criticism. Mark uncertainty where the text is incomplete.`,
      },
      chat: {
        label: 'Open question',
        description: 'Ask anything about the paper',
        instruction: `Answer the user's question directly and briefly. Cite the relevant section when possible. If the answer is not in the paper, say "Not stated in the article."`,
      },
    };

    const SEEDED_PROMPTS = {
      summary: ['Summarize the contribution in three sentences', 'What is the single most important finding?', 'What kind of study is this?'],
      claims: ['What does this paper actually establish?', 'What is the evidence base behind the main claim?', 'Where do the authors overreach, if anywhere?'],
      translation: ['Why should this reader care?', 'What would change in practice after reading this?', 'What should this reader NOT take away from this?'],
      appraisal: ['How rigorous is this study, honestly?', 'Do the methods support the conclusions drawn?', 'What would a reviewer ask the authors to revise?'],
      chat: ['What is an establishing operation, in plain terms?', 'Why is "how" harder to teach than "what" or "where"?', 'What happened with generalization across baselines?', 'How would a BCBA-SLP team use this paper together?'],
    };

    // ============================================================
    // ICONS (inline SVGs so we don't need a library)
    // ============================================================

    const IconBook = () => (
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="1.5" strokeLinecap="round" strokeLinejoin="round">
        <path d="M4 19.5v-15A2.5 2.5 0 0 1 6.5 2H20v20H6.5a2.5 2.5 0 0 1 0-5H20" />
      </svg>
    );

    const IconSparkles = () => (
      <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="1.5" strokeLinecap="round" strokeLinejoin="round">
        <path d="m12 3-1.9 5.8a2 2 0 0 1-1.287 1.288L3 12l5.8 1.9a2 2 0 0 1 1.288 1.287L12 21l1.9-5.8a2 2 0 0 1 1.287-1.288L21 12l-5.8-1.9a2 2 0 0 1-1.288-1.287Z" />
      </svg>
    );

    const IconSend = () => (
      <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="1.8" strokeLinecap="round" strokeLinejoin="round">
        <path d="m22 2-7 20-4-9-9-4Z" />
        <path d="M22 2 11 13" />
      </svg>
    );

    const IconLoader = () => (
      <svg className="spin" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round">
        <path d="M21 12a9 9 0 1 1-6.219-8.56" />
      </svg>
    );

    const IconReset = () => (
      <svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round">
        <path d="M3 12a9 9 0 1 0 9-9 9.75 9.75 0 0 0-6.74 2.74L3 8" />
        <path d="M3 3v5h5" />
      </svg>
    );

    // ============================================================
    // COMPONENT
    // ============================================================

    function InteractivePaper() {
      const [readerProfile, setReaderProfile] = useState('editor');
      const [mode, setMode] = useState('summary');
      const [messages, setMessages] = useState([]);
      const [input, setInput] = useState('');
      const [loading, setLoading] = useState(false);
      const chatEndRef = useRef(null);

      useEffect(() => {
        chatEndRef.current?.scrollIntoView({ behavior: 'smooth' });
      }, [messages, loading]);

      const sendMessage = async (userText) => {
        if (!userText.trim() || loading) return;

        const newMessages = [...messages, { role: 'user', content: userText }];
        setMessages(newMessages);
        setInput('');
        setLoading(true);

        const profile = READER_PROFILES[readerProfile];
        const modeConfig = MODES[mode];

        const composedSystem = `${SYSTEM_PROMPT}

${ARTICLE_CONTEXT}

READER PROFILE:
Role: ${profile.label}
Context: ${profile.description}
Tone: ${profile.tone}

RESPONSE MODE: ${modeConfig.label}
${modeConfig.instruction}`;

        try {
          const response = await fetch('/api/claude', {
            method: 'POST',
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify({
              system: composedSystem,
              messages: newMessages.map((m) => ({ role: m.role, content: m.content })),
            }),
          });

          const data = await response.json();

          if (data.error) {
            setMessages([...newMessages, { role: 'assistant', content: `Error: ${data.error}` }]);
            return;
          }

          const assistantText = data.content.filter((b) => b.type === 'text').map((b) => b.text).join('\n');
          setMessages([...newMessages, { role: 'assistant', content: assistantText }]);
        } catch (err) {
          setMessages([...newMessages, { role: 'assistant', content: 'Could not reach the reading layer. Try again in a moment.' }]);
        } finally {
          setLoading(false);
        }
      };

      const resetChat = () => setMessages([]);

      return (
        <div style={{ minHeight: '100vh', background: '#F5F2EC' }}>
          <header style={{ borderBottom: '1px solid #D4C9B5', padding: '14px 32px', display: 'flex', justifyContent: 'space-between', alignItems: 'center', background: '#F5F2EC', position: 'sticky', top: 0, zIndex: 10 }}>
            <div style={{ display: 'flex', alignItems: 'center', gap: '10px' }}>
              <IconBook />
              <span style={{ fontFamily: 'Raleway, sans-serif', fontSize: '0.68rem', letterSpacing: '0.25em', textTransform: 'uppercase', fontWeight: 500 }}>The Interactive Paper</span>
            </div>
            <div style={{ fontFamily: 'Raleway, sans-serif', fontSize: '0.65rem', letterSpacing: '0.2em', textTransform: 'uppercase', color: '#6B5D4F' }}>Demo · Shillingsburg &amp; Valentino 2011</div>
          </header>

          <div className="split" style={{ display: 'grid', gridTemplateColumns: '1.15fr 1fr', minHeight: 'calc(100vh - 51px)' }}>
            <div className="paper-pane" style={{ borderRight: '1px solid #D4C9B5', padding: '56px 64px 80px 64px', overflowY: 'auto', maxHeight: 'calc(100vh - 51px)' }}>
              <div style={{ maxWidth: '580px', margin: '0 auto' }}>
                <div style={{ fontFamily: 'Raleway, sans-serif', fontSize: '0.65rem', letterSpacing: '0.22em', textTransform: 'uppercase', color: '#6B5D4F', marginBottom: '32px' }}>{PAPER.journal} · Vol. {PAPER.volume} · {PAPER.year}</div>
                <h1 style={{ fontFamily: 'Lora, Georgia, serif', fontSize: '2.05rem', lineHeight: 1.2, fontWeight: 600, margin: '0 0 20px 0', letterSpacing: '-0.01em' }}>{PAPER.title}</h1>
                <div style={{ fontFamily: 'Lora, serif', fontStyle: 'italic', fontSize: '1.02rem', color: '#3D4B5C', marginBottom: '8px' }}>{PAPER.authors}</div>
                <div style={{ fontFamily: 'Raleway, sans-serif', fontSize: '0.78rem', color: '#6B5D4F', marginBottom: '44px', letterSpacing: '0.02em' }}>{PAPER.affiliation}</div>

                <div style={{ padding: '24px 28px', background: '#EBE6DB', borderLeft: '2px solid #0A4D5C', marginBottom: '44px', fontSize: '0.92rem', lineHeight: 1.7 }}>
                  <div style={{ fontFamily: 'Raleway, sans-serif', fontSize: '0.68rem', letterSpacing: '0.22em', textTransform: 'uppercase', color: '#6B5D4F', marginBottom: '10px', fontWeight: 600 }}>Abstract</div>
                  {PAPER.abstract}
                </div>

                <div className="paper-body" style={{ fontSize: '0.98rem', color: '#1A2B3C' }}>
                  <h3>Introduction</h3>
                  {PAPER.sections.introduction.split('\n\n').map((p, i) => <p key={`intro-${i}`}>{p}</p>)}
                  <h3>Method</h3>
                  {PAPER.sections.method.split('\n\n').map((p, i) => <p key={`method-${i}`}>{p}</p>)}
                  <h3>Results</h3>
                  {PAPER.sections.results.split('\n\n').map((p, i) => <p key={`results-${i}`}>{p}</p>)}
                  <h3>Discussion</h3>
                  {PAPER.sections.discussion.split('\n\n').map((p, i) => <p key={`disc-${i}`}>{p}</p>)}
                  <h3>Limitations</h3>
                  {PAPER.sections.limitations.split('\n\n').map((p, i) => <p key={`lim-${i}`}>{p}</p>)}
                </div>
              </div>
            </div>

            <div style={{ display: 'flex', flexDirection: 'column', background: '#FCFAF5', maxHeight: 'calc(100vh - 51px)' }}>
              <div style={{ padding: '24px 32px 20px 32px', borderBottom: '1px solid #D4C9B5' }}>
                <div style={{ display: 'flex', alignItems: 'center', gap: '10px', marginBottom: '18px' }}>
                  <span style={{ color: '#0A4D5C', display: 'flex' }}><IconSparkles /></span>
                  <span style={{ fontFamily: 'Raleway, sans-serif', fontSize: '0.68rem', letterSpacing: '0.22em', textTransform: 'uppercase', fontWeight: 600, color: '#0A4D5C' }}>Reading Layer</span>
                  {messages.length > 0 && (
                    <button onClick={resetChat} style={{ marginLeft: 'auto', background: 'transparent', border: 'none', color: '#6B5D4F', fontFamily: 'Raleway, sans-serif', fontSize: '0.7rem', letterSpacing: '0.1em', textTransform: 'uppercase', cursor: 'pointer', display: 'flex', alignItems: 'center', gap: '4px' }}>
                      <IconReset /> Reset
                    </button>
                  )}
                </div>

                <div style={{ marginBottom: '16px' }}>
                  <label style={{ display: 'block', fontFamily: 'Raleway, sans-serif', fontSize: '0.62rem', letterSpacing: '0.22em', textTransform: 'uppercase', color: '#6B5D4F', marginBottom: '8px', fontWeight: 500 }}>Reader</label>
                  <div style={{ display: 'flex', flexWrap: 'wrap', gap: '6px' }}>
                    {Object.entries(READER_PROFILES).map(([key, p]) => (
                      <button key={key} className="profile-btn" onClick={() => setReaderProfile(key)} style={{ padding: '6px 12px', fontSize: '0.78rem', border: '1px solid', borderColor: readerProfile === key ? '#0A4D5C' : '#D4C9B5', background: readerProfile === key ? '#0A4D5C' : 'transparent', color: readerProfile === key ? '#F5F2EC' : '#1A2B3C', borderRadius: '2px', fontWeight: readerProfile === key ? 600 : 400 }}>{p.label}</button>
                    ))}
                  </div>
                </div>

                <div>
                  <label style={{ display: 'block', fontFamily: 'Raleway, sans-serif', fontSize: '0.62rem', letterSpacing: '0.22em', textTransform: 'uppercase', color: '#6B5D4F', marginBottom: '8px', fontWeight: 500 }}>Mode</label>
                  <div style={{ display: 'flex', flexWrap: 'wrap', gap: '6px' }}>
                    {Object.entries(MODES).map(([key, m]) => (
                      <button key={key} className="mode-btn" onClick={() => setMode(key)} style={{ padding: '6px 12px', fontSize: '0.78rem', border: '1px solid', borderColor: mode === key ? '#B8962E' : '#D4C9B5', background: mode === key ? '#B8962E' : 'transparent', color: mode === key ? '#FCFAF5' : '#1A2B3C', borderRadius: '2px', fontWeight: mode === key ? 600 : 400 }}>{m.label}</button>
                    ))}
                  </div>
                  <div style={{ fontFamily: 'Lora, serif', fontStyle: 'italic', fontSize: '0.8rem', color: '#6B5D4F', marginTop: '8px' }}>{MODES[mode].description}</div>
                </div>
              </div>

              <div className="chat-scroll" style={{ flex: 1, overflowY: 'auto', padding: '24px 32px' }}>
                {messages.length === 0 && (
                  <div style={{ maxWidth: '460px' }}>
                    <div style={{ fontFamily: 'Lora, serif', fontStyle: 'italic', fontSize: '0.95rem', lineHeight: 1.7, color: '#3D4B5C', marginBottom: '24px' }}>
                      Ask the paper a question. Responses are grounded in the article only, and analytical claims are labeled as <span className="epistemic-supported">supported</span>, <span className="epistemic-inference">inferred</span>, or <span className="epistemic-notstated">not stated</span>.
                    </div>
                    <div style={{ fontFamily: 'Raleway, sans-serif', fontSize: '0.62rem', letterSpacing: '0.22em', textTransform: 'uppercase', color: '#6B5D4F', marginBottom: '12px', fontWeight: 500 }}>Suggested prompts</div>
                    <div style={{ display: 'flex', flexDirection: 'column', gap: '8px' }}>
                      {SEEDED_PROMPTS[mode].map((prompt, i) => (
                        <button key={i} className="seed-btn" onClick={() => sendMessage(prompt)} style={{ textAlign: 'left', padding: '12px 16px', background: 'transparent', border: '1px solid #D4C9B5', borderRadius: '2px', fontFamily: 'Lora, serif', fontSize: '0.9rem', color: '#1A2B3C', cursor: 'pointer' }}>{prompt}</button>
                      ))}
                    </div>
                  </div>
                )}

                {messages.map((m, i) => (
                  <div key={i} className="msg" style={{ marginBottom: '24px' }}>
                    {m.role === 'user' ? (
                      <div>
                        <div style={{ fontFamily: 'Raleway, sans-serif', fontSize: '0.6rem', letterSpacing: '0.22em', textTransform: 'uppercase', color: '#6B5D4F', marginBottom: '6px', fontWeight: 600 }}>{READER_PROFILES[readerProfile].label}</div>
                        <div style={{ fontFamily: 'Lora, serif', fontSize: '0.98rem', lineHeight: 1.6, padding: '12px 16px', background: '#EBE6DB', borderLeft: '2px solid #6B5D4F' }}>{m.content}</div>
                      </div>
                    ) : (
                      <div>
                        <div style={{ fontFamily: 'Raleway, sans-serif', fontSize: '0.6rem', letterSpacing: '0.22em', textTransform: 'uppercase', color: '#0A4D5C', marginBottom: '6px', fontWeight: 600 }}>Reading Layer · {MODES[mode].label}</div>
                        <div style={{ fontFamily: 'Lora, serif', fontSize: '0.95rem', lineHeight: 1.7, whiteSpace: 'pre-wrap', color: '#1A2B3C' }} dangerouslySetInnerHTML={{ __html: m.content.replace(/(Supported by the paper)(:|\b)/gi, '<span class="epistemic-supported">$1</span>$2').replace(/(Inference from the paper|Reasonable inference)(:|\b)/gi, '<span class="epistemic-inference">$1</span>$2').replace(/(Not stated in the paper|Not stated in the article|Unknown or not stated)(:|\b)/gi, '<span class="epistemic-notstated">$1</span>$2') }} />
                      </div>
                    )}
                  </div>
                ))}

                {loading && (
                  <div style={{ marginBottom: '24px' }}>
                    <div style={{ fontFamily: 'Raleway, sans-serif', fontSize: '0.6rem', letterSpacing: '0.22em', textTransform: 'uppercase', color: '#0A4D5C', marginBottom: '6px', fontWeight: 600 }}>Reading Layer</div>
                    <div style={{ padding: '12px 16px' }}>
                      <span className="pulse" /><span className="pulse" /><span className="pulse" />
                    </div>
                  </div>
                )}
                <div ref={chatEndRef} />
              </div>

              <div style={{ padding: '16px 32px 24px 32px', borderTop: '1px solid #D4C9B5', background: '#FCFAF5' }}>
                <div style={{ display: 'flex', gap: '8px', alignItems: 'flex-end' }}>
                  <textarea
                    value={input}
                    onChange={(e) => setInput(e.target.value)}
                    onKeyDown={(e) => { if (e.key === 'Enter' && !e.shiftKey) { e.preventDefault(); sendMessage(input); } }}
                    placeholder="Ask the paper a question..."
                    rows={1}
                    style={{ flex: 1, padding: '12px 14px', fontFamily: 'Lora, serif', fontSize: '0.95rem', border: '1px solid #D4C9B5', borderRadius: '2px', background: '#F5F2EC', resize: 'none', outline: 'none', color: '#1A2B3C', lineHeight: 1.5, minHeight: '44px', maxHeight: '120px' }}
                    disabled={loading}
                  />
                  <button className="send-btn" onClick={() => sendMessage(input)} disabled={loading || !input.trim()} style={{ background: '#0A4D5C', color: '#F5F2EC', border: 'none', borderRadius: '2px', padding: '0 16px', height: '44px', cursor: 'pointer', display: 'flex', alignItems: 'center', justifyContent: 'center' }}>
                    {loading ? <IconLoader /> : <IconSend />}
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>
      );
    }

    ReactDOM.createRoot(document.getElementById('root')).render(<InteractivePaper />);
  </script>
</body>
</html>
