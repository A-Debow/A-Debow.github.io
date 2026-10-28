---
layout: page
title: AI-Powered Call Center Analytics Platform
description: An end-to-end platform to transcribe, analyze, and visualize call center audio using Transformer-based NLP models and a fine-tuned classifier.
img: assets/img/call_center_platform.png
importance: 1
category: Intelligent Systems & User Experience
---

<p>Call center managers face a significant challenge in effectively analyzing the vast volume of audio calls to extract actionable insights. This project presents an intelligent, AI-driven analytics platform that fully automates the process, from converting audio files into structured transcripts to analyzing them with Transformer models and culminating in an interactive API for querying results.</p>
<hr>
<h3 id="1-system-architecture--pipeline">1. System Architecture & Pipeline</h3>
<p>The system was designed as an integrated pipeline consisting of several logical phases, each built upon state-of-the-art technologies in Natural Language Processing (NLP) and Deep Learning.</p>

<h5 class="mt-4">Phase 1: Speech-to-Text with Speaker Diarization</h5>
<p>The foundation of the project is the accurate conversion of audio into text. The advanced WhisperX model was chosen for this task due to its ability to provide high-accuracy transcription along with Speaker Diarization, which automatically identifies and separates the customer's speech from the agent's—a critical step for all subsequent analysis.</p>

<h5 class="mt-4">Phase 2: Text Analysis with Transformer Models</h5>
<p>Once structured text was obtained, a suite of pre-trained Transformer models, served via a FastAPI application, was used to extract key features like Abstractive Summarization (<code>facebook/bart-large-cnn</code>), Sentiment Analysis (<code>cardiffnlp/twitter-roberta-base-sentiment-latest</code>), and initial Call Outcome Classification (Zero-Shot with <code>facebook/bart-large-mnli</code>).</p>
<hr>
<h3 id="2-custom-deep-learning-for-outcome-classification">2. Custom Deep Learning for Outcome Classification</h3>
<p>To achieve superior accuracy in determining if a customer's problem was resolved, a custom solution was developed. A <code>DistilBERT</code> model was fine-tuned on a large, tailored dataset (<code>AIxBlock/92k-real-world-call-center-scripts-english</code>), learning the specific patterns of support dialogues to create a highly specialized and accurate classifier.</p>
<div class="row justify-content-center">
    <div class="col-sm-10 col-md-8">
        <figure>
          <picture><img src="/assets/img/call_center_model_architecture.png" class="img-fluid rounded z-depth-1" alt="Diagram of the Custom Hierarchical Model Architecture" loading="lazy"></picture>
          <figcaption class="caption">Architecture of the custom Deep Learning model for outcome classification.</figcaption>
        </figure>
    </div>
</div>
<hr>
<h3 id="3-rag-powered-interactive-chatbot">3. RAG-Powered Interactive Chatbot</h3>
<p>To make the analyzed data queryable, an advanced chatbot was developed using a Retrieval-Augmented Generation (RAG) architecture. This chatbot searches the knowledge base of call summaries to find information relevant to a user's query and then uses the <code>t5-base</code> model to generate a natural, concise answer supported by sources.</p>
<div class="row justify-content-center">
    <div class="col-sm-10 col-md-8">
        <figure>
          <picture><img src="/assets/img/call_center_rag_diagram.png" class="img-fluid rounded z-depth-1" alt="Diagram of the RAG Chatbot Architecture" loading="lazy"></picture>
          <figcaption class="caption">Workflow of the Retrieval-Augmented Generation (RAG) chatbot.</figcaption>
        </figure>
    </div>
</div>
<hr>
<h3 id="technical-summary">Technical Summary</h3>
<ul>
  <li><strong>Speech-to-Text:</strong> WhisperX with Speaker Diarization</li>
  <li><strong>NLP Analysis:</strong> Transformers (BART, RoBERTa), Zero-Shot Classification</li>
  <li><strong>Custom Model:</strong> Fine-tuned DistilBERT with TensorFlow/Keras</li>
  <li><strong>Chatbot:</strong> Retrieval-Augmented Generation (RAG) with T5</li>
  <li><strong>Backend:</strong> FastAPI</li>
</ul>
<hr>
<h3 id="team-members">Team Members</h3>
<ul>
  <li>Ahmad Debow</li>
  <li>Sami Farah</li>
</ul>
