# Pythonの公式イメージを使用
FROM python:3.11

WORKDIR /app

# MySQLクライアントのビルドに必要な依存関係をインストール
RUN apt-get update && apt-get install -y default-libmysqlclient-dev build-essential

# 仮想環境を作成してPATHに追加（/opt/venvに置くのが一般的）
RUN python -m venv /opt/venv
ENV PATH="/opt/venv/bin:$PATH"

# requirements.txtをコピーして、仮想環境にインストール
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

# アプリケーションのコードをコピー
COPY . .

# manage.py があるかどうかで処理を分ける
CMD ["sh", "-c", "if [ -f manage.py ]; then python manage.py runserver 0.0.0.0:8000; else django-admin startproject config . && python manage.py startapp api && python manage.py runserver 0.0.0.0:8000; fi"]
