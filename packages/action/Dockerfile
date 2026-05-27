FROM oven/bun:1

RUN apt-get update \
  && apt-get install -y --no-install-recommends git \
  && rm -rf /var/lib/apt/lists/*

WORKDIR /action

# The build context for a GitHub Docker action is the directory containing
# the Dockerfile (packages/action/), not the repo root.
COPY package.json tsconfig.json ./
COPY src ./src

RUN bun install --production

ENTRYPOINT ["bun", "run", "/action/src/index.ts"]
