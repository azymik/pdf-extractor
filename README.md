docker buildx build $(cat .devpass.env | sed 's@^@--build-arg @g' | paste -s -d " " /dev/stdin) --progress=plain --no-cache --pull -t azymik/pdf-extractor .

docker buildx build $(cat .devpass.env | sed 's@^@--build-arg @g' | paste -s -d " " /dev/stdin) --progress=plain -t azymik/pdf-extractor .

docker container run -it --rm -v ./:/app azymik/pdf-extractor
