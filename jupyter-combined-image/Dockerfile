FROM rocker/binder

RUN pip install jupyterlab-visualpython
RUN pip install jupyter-ai langchain-ollama

#add visual python related dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

#install data catalog extension
COPY fetchextension-0.1.0.tar.gz .
RUN pip install fetchextension-0.1.0.tar.gz

COPY jupyter_jupyter_ai_config.json /etc/jupyter/jupyter_jupyter_ai_config.json
 
# Switch back to jovyan to avoid accidental container runs as root
USER ${NB_UID}
