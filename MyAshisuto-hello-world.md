# discover latent emotion triggers in sales audio recordings
```mermaid
graph TD;
subgraph supercog
	subgraph source
		Cloud-Storage
		end
	subgraph input
		Cloud-Storage --> Audio-File
		end
  	subgraph LLM/API Processing
  		Audio-File --> speaker-diarization & speech-to-text & Emotion-Logic-Arousal --> LLM-fusion
		LLM-fusion --> time-series-analysis & context-analysis --> Arousal-to-self --> consistent & inconsistent
consistent --- high-self & high-other & low-self & low-other
  end
  subgraph storage
    speaker-diarization & speech-to-text & Emotion-Logic-Arousal --> KG-database
  LLM-fusion & time-series-analysis --> KG-database
  end
  subgraph output
  time-series-analysis --> Annotated-Transcript --> Transcript & Speaker-ID & arousal-annotated-keywords/phrases
  time-series-analysis --> 2D-arousal-time-series-chart --> key-arousal-triggers --> global-max & global-min & global-avg --> Annotated-Transcript
Arousal-to-self --> 2D-graph
key-arousal-triggers --> local-maxes & local-mins --> Annotated-Transcript
	end
```
