<chained-prompts>

  <!-- 
    SECTION A: Introduction and High-Level Overview
    - Start of the chain
    - The output is stored in "outputA"
  -->
  <prompt id="SECTION_A">
    <title>Introduction and High-Level Overview</title>
    <instructions>
      <![CDATA[
      1. Provide a high-level introduction to the domain (e.g., "Quantum Computing").
      2. Outline the fundamental goals: exploring fundamentals, ecosystem, key players, disruptions, scenarios, etc.
      3. Wait for a complete response.
      4. Store the response in "outputA".
      ]]>
    </instructions>
    <nextPrompt>SECTION_B</nextPrompt>
  </prompt>

  <!--
    SECTION B: Fundamentals & Layered Ecosystem
    - Use outputA as context for deeper fundamentals and layered breakdown
    - Store new output in "outputB"
  -->
  <prompt id="SECTION_B">
    <title>Detailed Fundamentals and Layered Ecosystem</title>
    <instructions>
      <![CDATA[
      1. Use the entire text from "outputA" as context (but do not reproduce it verbatim).
      2. Expand on fundamentals (qubits, superposition, entanglement, decoherence, etc.)
         and the multi-layer ecosystem (materials, hardware, control systems, middleware,
         software, end-user apps).
      3. Provide a consolidated table in Markdown capturing each layer's roles, major players,
         dependencies, and vulnerabilities.
      4. Wait for a complete response.
      5. Store the response in "outputB".
      ]]>
    </instructions>
    <nextPrompt>SECTION_C</nextPrompt>
  </prompt>

  <!--
    SECTION C: Key Players and Investment Perspectives
    - Build on "outputB" (ecosystem) to detail major industry players
    - Store new output in "outputC"
  -->
  <prompt id="SECTION_C">
    <title>Key Players and Investment Perspectives</title>
    <instructions>
      <![CDATA[
      1. Using "outputB" (the fundamentals + layered ecosystem) as context:
         - Identify major domain players (companies, labs, consortia).
         - For each: unique value, public/private, approximate valuations if known,
           major risks, moats or differentiators, and relevant links.
      2. Provide a table in Markdown covering these details.
      3. Wait for a complete response.
      4. Store the response in "outputC".
      ]]>
    </instructions>
    <nextPrompt>SECTION_D</nextPrompt>
  </prompt>

  <!--
    SECTION D: Cross-Layer Disruptions & Scenario Planning
    - Use "outputC" as context to show how disruptions might affect each player
    - Provide scenario framework. Store in "outputD"
  -->
  <prompt id="SECTION_D">
    <title>Cross-Layer Disruptions & Scenario Planning</title>
    <instructions>
      <![CDATA[
      1. Use "outputC" (players info) as context:
         - Discuss potential breakthroughs/bottlenecks (e.g., new materials, cryogenics shortage,
           topological qubit setbacks, quantum winter) and how these ripple through the entire ecosystem.
      2. Present a scenario planning framework (e.g., Slow/Low, Slow/High, Rapid/Low, Rapid/High).
      3. Include strategic actions or recommendations for each scenario.
      4. Wait for a complete response.
      5. Store the response in "outputD".
      ]]>
    </instructions>
    <nextPrompt>SECTION_E</nextPrompt>
  </prompt>

  <!--
    SECTION E: Final Synthesis or Next Steps
    - Summarize or provide next steps based on scenario planning
    - Store new output in "outputE"
  -->
  <prompt id="SECTION_E">
    <title>Summary or Next Steps</title>
    <instructions>
      <![CDATA[
      1. Use "outputD" (scenarios) to craft final recommendations or next steps for a leader/investor.
      2. Summarize immediate action items (e.g., R&D diversification, supply-chain security, cryptographic readiness).
      3. Wait for a complete response.
      4. Store the response in "outputE".
      ]]>
    </instructions>
    <nextPrompt>SECTION_F</nextPrompt>
  </prompt>

  <!--
    SECTION F: Very Detailed Technical Reports
    - Each builds on the fundamentals in "outputE"
    - Expand references (articles, books, videos). Provide a plan for technical artifacts.
    - Store new output in "outputF"
  -->
  <prompt id="SECTION_F">
    <title>Very Detailed Technical Reports</title>
    <instructions>
      <![CDATA[
      1. Use "outputE" (overall summary) as context.
      2. Create a plan for extremely detailed technical reports on each layer (foundation, hardware, control, etc.),
         capturing every nuance. Each report should build on the previous.
      3. Provide references (academic articles, textbooks, conference papers, YouTube/online lectures) 
         for each sub-topic. Suggest ways to store or host these technical artifacts (wikis, docs, etc.).
      4. Wait for a complete response.
      5. Store the response in "outputF".
      ]]>
    </instructions>
    <nextPrompt>SECTION_G</nextPrompt>
  </prompt>

  <!--
    SECTION G: Very Detailed Financial Reports
    - Expand on cost models, ROI timelines, public vs private valuations, 
      synergy with HPC or cloud business lines. 
    - Store in "outputG"
  -->
  <prompt id="SECTION_G">
    <title>Very Detailed Financial Reports</title>
    <instructions>
      <![CDATA[
      1. Use "outputF" as context, focusing on the financial dimension:
         - Provide in-depth analyses: cost structures, ROI modeling, current valuations,
           short & long-term forecasts, synergy with HPC or cloud businesses.
      2. Include references to major consulting or financial reports (e.g., McKinsey, Deloitte, 
         publicly available investor presentations).
      3. Suggest how to maintain a living "financial dossier" that tracks these metrics over time.
      4. Wait for a complete response.
      5. Store the response in "outputG".
      ]]>
    </instructions>
    <nextPrompt>SECTION_H</nextPrompt>
  </prompt>

  <!--
    SECTION H: Government & Policy Implications
    - Summarize legislative or policy considerations, public funding, national security angles
    - Use "outputG" as context, store new output in "outputH"
  -->
  <prompt id="SECTION_H">
    <title>Government & Policy Implications</title>
    <instructions>
      <![CDATA[
      1. Building on "outputG" (financial perspective), detail the government and policy angles:
         - Public funding programs (e.g., US National Quantum Initiative, EU Quantum Flagship, 
           China's quantum agenda), national security considerations, export controls, etc.
      2. Provide references to official government documents or high-level policy papers.
      3. Wait for a complete response.
      4. Store the response in "outputH".
      ]]>
    </instructions>
    <nextPrompt>SECTION_I</nextPrompt>
  </prompt>

  <!--
    SECTION I: Expanded Investment Rationale
    - Tie in the technical, financial, and policy aspects to craft a deep investment rationale.
    - Use "outputH" as context, store new output in "outputI"
  -->
  <prompt id="SECTION_I">
    <title>Expanded Investment Rationale</title>
    <instructions>
      <![CDATA[
      1. Use "outputH" (policy context) to refine a comprehensive investment rationale.
      2. Consider risk factors, moats, synergy with AI or HPC, plus any new references to investor case studies.
      3. Provide a bullet-point set of reasons to invest or stay cautious, referencing 
         earlier financial data and scenario planning.
      4. Wait for a complete response.
      5. Store the response in "outputI".
      ]]>
    </instructions>
    <nextPrompt>SECTION_J</nextPrompt>
  </prompt>

  <!--
    SECTION J: Best Places to Learn & Approach to Master the Industry
    - Provide a learning roadmap from "outputI"
    - Store new output in "outputJ"
  -->
  <prompt id="SECTION_J">
    <title>Best Learning Resources & Industry Approach</title>
    <instructions>
      <![CDATA[
      1. Using "outputI" as context, outline the best places to learn more:
         - Books, academic courses, online platforms, conferences, 
           recommended reading sequences, practical labs or cloud-based practice.
      2. Suggest how different roles (executive, investor, engineer, student) might approach learning.
      3. Wait for a complete response.
      4. Store the response in "outputJ".
      ]]>
    </instructions>
    <nextPrompt>SECTION_K</nextPrompt>
  </prompt>

  <!--
    SECTION K: Executive 6-Pager & One-Paragraph Headline
    - Summarize everything in a concise 6-page style doc + a catchy 1-paragraph teaser
    - End of chain
  -->
  <prompt id="SECTION_K">
    <title>Executive 6-Pager & Catchy Headline</title>
    <instructions>
      <![CDATA[
      1. Using "outputJ" (learning roadmap) plus all prior context, compile an executive report in ~6 pages:
         - Summarize the entire field, from fundamentals to financial, policy, investment rationales, etc.
      2. Create a short, catchy 1-paragraph headline or teaser that could be used to promote this 
         6-pager on social media or in an internal newsletter.
      3. Wait for a complete response.
      4. End of chain (no further prompt).
      ]]>
    </instructions>
    <nextPrompt>NONE</nextPrompt>
  </prompt>

</chained-prompts>
