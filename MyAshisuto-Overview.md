# discover latent emotion triggers in sales audio recordings & reason about possibilities at each point 
```mermaid
graph TD;
  user --> audio
  subgraph single-loop-analysis
    audio --> extractions --> time-series-analysis --> arousal-to-self-other-analysis & arousal-location & arousal-environment --> trigger-anomaly-analysis 
    end
  subgraph double-loop-analysis
    trigger-anomaly-analysis --> multi-agent-explanation-debate --> grounding-search-API --> result-entropy-analysis --> multi-agent-explanation-debate --> summary & annotated-transcript
    end
  subgraph user-feedback
    trigger-anomaly-analysis --> 2D-graph & 3D-time
    annotated-transcript & summary --> user
    2D-graph & 3D-time --> user --> positive-feedback & negative-feedback & other-feedback-reactions
    other-feedback-reactions --> audio
    positive-feedback & negative-feedback --> result-entropy-analysis & 2D-graph
    end 
```
