# demo

Build components

```bash
viash ns build --setup cb
```

Run native

```bash
target/native/foo/foo --input README.md --output README_copy.md
```

Run docker

```bash
target/docker/foo/foo --input README.md --output README_copy2.md
```

## manually disable docker

```bash
docker rmi foo:latest
sed -i 's#cat << VIASHEOF | eval.*#cat << VIASHEOF | bash#; s#/viash_automount##g' target/docker/foo/foo
target/docker/foo/foo --input README.md --output README_copy3.md
```