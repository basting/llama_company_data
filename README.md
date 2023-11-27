## [Super Quick: Retrieval Augmented Generation (RAG) with Llama 2.0 on Company Information using CPU](https://python.plainenglish.io/super-quick-building-your-own-custom-llama-on-company-information-5d7af78d1999)

### Software Specs
- Operating System: Ubuntu preferably
- Python: version 3.10 and above
- Model: Quantized [llama-2–7B-Chat-GGML](https://huggingface.co/TheBloke/Llama-2-7B-Chat-GGML/blob/main/llama-2-7b-chat.ggmlv3.q8_0.bin) (so that it can run on CPU)
- Vector Data Store: FAISS
- Transformer: CTransformer
- Deployment: Chainlit

### Hardware Requirement
- Hard Disk Space: The llama model is ~7GB, the rest is your data.
- RAM: 16GB at least (8 GB will fail after one or two questions)

### Setup Project
- Download the llama2 model into the root folder. The model is linked above.
- Run `pip install -r requirements.txt`
- Create a `web_data` folder
- Run `python extract_data.py` to scrape the html and pdf files present in a company domain
  - Update the domain as needed in the file
- Run `python ingest.py` to ingest the data from the web_data folder
- Deploy Mode (use one of the below options): 
  - Run `chainlit run deploy.py -w` <br>
    OR
  - Run `python -m chainlit run deploy.py -w`
- App will be available on http://localhost:8000