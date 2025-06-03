FROM rocm/pytorch:latest
RUN pip install notebook
EXPOSE 8888
# --notebook-dir=$WORKSPACE
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--no-browser", "--allow-root"]