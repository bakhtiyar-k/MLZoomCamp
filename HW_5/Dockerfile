FROM svizor/zoomcamp-model:3.10.12-slim

RUN pip install poetry
RUN pip install waitress

WORKDIR /app
COPY poetry.lock pyproject.toml /app/

RUN poetry config virtualenvs.create false \
    && poetry install

COPY predict_credit_model2.py /app/

EXPOSE 9696

ENTRYPOINT [ "waitress-serve", "--listen=0.0.0.0:9696", "predict_credit_model2:app"]

