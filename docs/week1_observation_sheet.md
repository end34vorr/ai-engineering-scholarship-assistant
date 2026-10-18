Week 1 Observation Sheet — YouTube Recommendations System name YouTube Recommendations (Home feed) 

Group members Arif Iskandar, Danish Iqbal, Wan Alif Danial 

1\. What problem does this system solve? Who benefits? Problem: The volume of videos on YouTube is far too large for a user to search through manually. The recommendation system helps users discover relevant content without having to know what to search for and helps creators get their videos in front of interested viewers. Beneficiaries: • Viewers: save time finding content and discover new topics. • Creators: gain reach beyond their existing subscribers. • YouTube / advertisers: higher watch time and engagement, which supports ad revenue. 



2\. Which AI stack layer is most visible to users? Layer: Application / Model / Infrastructure  Explanation: Users only see the Home feed, the "Up next" panel, and the video cards (thumbnail, title, channel). The ranking and recommendation models that decide what appears (the model layer) and the data pipelines and serving systems behind them (the infrastructure layer) are invisible. The only window into the model layer is the small "Why this video?" style explanation and feedback controls (e.g. "Not interested", "Don't recommend channel"). 



3\. Quality dimensions (at least 3, with measurement method) Dimension 1: Personalisation relevance Measure: Take the first 15 videos on the Home feed and mark each as relevant / not relevant to user’s real interests. Relevance rate = relevant / total. (Result: 14/15 = 93.33%) Dimension 2: Responsiveness to new signals (feed adaptation) Measure: Record the feed before and after searching something unusual (“cooking food”). Count how many of the top 15 videos are related to the new topic after 10 minutes. (Before: 0 videos, After: 4 videos) Dimension 3: Transparency / explainability Measure: Watch a video; count how many seconds and number of clicks needed until the feed adapts. (Result: with 60 seconds and 1 click, the feed recommends 4 cooking videos in the first 15 recommendation videos) Dimension 4: Diversity and fairness of exposure Measure: Proportion of distinct channels and topics in the top 15 videos, and whether small creators appear versus only large channels. (Result: 15 distinct channels, 7 topics, and large channels dominate the Home feed, small creators appear only if I have watched the content from that channel) 



4\. What did the system do WELL? Give a specific example. Observed: By default, the Home feed showed all interested topics from the user from the subscribed and new channel. After searching for “cooking food”, click, and watch 1 video for 60 seconds, the Home feed recommends 4 cooking videos, which matches the recent history in cooking topic. Evidence: Home feed – Before Searching for new topic Home Feed – After Searching for “cooking food” Hypothesis (not directly observed): The system likely used my watch history and search history to match this video, since the topic aligns with tech, games, music, podcasts and football. After searching for “cooking food”, the feed adapted, which suggests recent signals are weighted heavily. 



5\. What did it do POORLY? Give a specific example. Observed: After the unusual search, the feed instantly narrow the recommendation towards the recent search, which not necessarily be the user interest (might be accidental or shareddevice viewing). Hypothesis (not directly observed): The system may be optimising for engagement (watch time / clicks) rather than diversity, which could explain why it recommends according to the recent search, although the watch time just within 60 seconds. This cannot be confirmed from outside the system. 



6\. Responsible AI risks (at least 2). Who is harmed and how? Risk 1 — Filter bubble / narrowing of content (Fairness \& Societal harm): The system keeps recommending content like past behaviour, so users see a narrower range of views and topics over time. Who is harmed: viewers (reduced exposure to diverse information), and society if this reinforces polarised or one-sided views. Risk 2 — Harmful or inappropriate content exposure (Safety): An engagement-driven recommender can surface sensational, misleading, or age-inappropriate content because it attracts clicks. Who is harmed: especially young users, who may be led toward harmful, polarizing or ragebaiting content. Risk 3 — Privacy and profiling (Privacy) / Lack of transparency (Transparency \& Accountability): Recommendations depend on detailed watch, search, and interaction history, creating a sensitive behavioural profile; users have limited visibility into what data drives each recommendation or how to fully control it. Who is harmed: all users, whose interests, habits, and possibly sensitive attributes can be inferred without clear understanding or consent. 



7\. If you could fix ONE thing, what and why? Fix: Provide a clear, specific, one-tap explanation on every recommended video (e.g. "Recommended because you watched \[VIDEO X]" plus the data signals used), together with a simple control to remove that signal from the user's profile. Why: This directly improves transparency and user control, and also helps reduce the filterbubble and privacy risks: users can understand and correct why they are seeing certain content, and can break a narrowing loop themselves. It is also feasible to implement because the system already has the underlying signals; they just need to be exposed in the interface. 

