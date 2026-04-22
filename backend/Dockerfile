FROM node:20-slim

WORKDIR /app

# Enable corepack en yarn
RUN corepack enable

# Copy package files
COPY package.json yarn.lock .yarnrc.yml ./
COPY .yarn ./.yarn

# Install dependencies
RUN yarn install --immutable

# Copy source code
COPY . .

# Build de applicatie (admin + backend)
RUN yarn build

# Start commando
CMD yarn medusa db:migrate && yarn start