FROM oven/bun:1

RUN apt-get update \
  && apt-get install -y --no-install-recommends git ca-certificates \
  && rm -rf /var/lib/apt/lists/*

WORKDIR /action

COPY package.json tsconfig.json ./
COPY src ./src

RUN bun install --production

ENTRYPOINT ["bun", "run", "/action/src/index.ts"]
