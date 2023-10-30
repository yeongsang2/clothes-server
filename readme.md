# Getting start

## Prerequisites
* Docker
* docker-compose-pulugin

## Installation
```
git clone https://github.com/yeongsang2/clothes-server.git
cd clothes-server
```

## Submodule clone 
```
git clone https://github.com/yeongsang2/app.git
git clone https://github.com/yeongsang2/app2.git
```
## Model weight download
```
git clone https://github.com/yeongsang2/object_storage.git
cd object_storage
mv *.pt ../app/resource
cd model
mv *.pb ../../app2/model/
mv variables ../../app2/model/
```

## openapi key
clothes-server/app/app/.env

```
LLM_MODEL=gpt-3.5-turbo # alternatively, gpt-4, text-davinci-003, etc
OPENAI_API_KEY=
OPENAI_TEMPERATURE=0.0

```
## Usage
* GPU
```
$ docker compose up --build
```
* cpu
```
$ docker compose up -f docker-compose-cpu.yml --build
```

### API Endpoint
* /clothes-classify
    * request
        * form-data(multipart/form-data)
        * key: file | value: image, key:tag | value: int 