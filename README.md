graph TD 
    A[任务需求] --> B{数据规模小？}
    B -->|是| C[TF-IDF + 浅层模型<br>（如SVM/LR）]
    B -->|否| D{需要上下文感知？}
    D -->|是| E[预训练模型<br>（BERT/RoBERTa）]
    D -->|否| F{需轻量化部署？}
    F -->|是| G[蒸馏模型<br>（如MiniLM/TinyBERT）]
    F -->|否| H[Word2Vec/GloVe + LSTM/CNN]
    
    %% 添加样式增强可读性
    classDef decision fill:#f9f,stroke:#333;
    classDef method fill:#bbf,stroke:#333,stroke-width:2px;
    class B,D,F decision;
    class C,E,G,H method;
