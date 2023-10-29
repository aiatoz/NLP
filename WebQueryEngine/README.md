
# Web Query Engine using LLM

- Components
    
    - Web Scraper
    - LLM
    Using an LLM to learn the  context from a web page, so that it can be used as a web querying engine.

- Limitations of the current system:
    - Due to limited compute I've restricted the context length to 2048. The default context length of 2048 will work just fine with a T4 GPU
    - If you have enough compute, feel free to increase the context length
    - The current scraping system is not efficient
        - We can use an LLM or a good filter to scrape out the required set of information so that it can be used for grounding
    - The LLM used here is 7b version of Mistral, we can use a better LLM to make the output much more reliable

- Tweaks
      
    - Context length can be increased by changing the value associated with "context_length" parameter
    - The code can be run completely locally with a good consumer end GPU. The model path has to be given in the code. 
            
      Eg : 
        Instead of 
            
            AutoModelForCausalLM.from_pretrained("TheBloke/Mistral-7B-Instruct-v0.1-GGUF", model_file="mistral-7b-instruct-v0.1.Q4_K_M.gguf", model_type = "mistral")
      Use       
        
            AutoModelForCausalLM.from_pretrained("model/mistral-7b-instruct-v0.1.Q4_K_M.gguf", model_type = "mistral")

            Where model/_model_name is the path in which the model bin/gguf file is stored.
      
        Check out the official Huggingface page for more details, URL : https://huggingface.co/TheBloke/Mistral-7B-Instruct-v0.1-GGUF

