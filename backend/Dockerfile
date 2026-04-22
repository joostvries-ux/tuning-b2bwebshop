FROM node:20

WORKDIR /app

# Copy alles
COPY . .

# Enable corepack en installeer yarn 4
RUN corepack enable && corepack prepare yarn@4.4.0 --activate

# Install dependencies
RUN yarn install

# Build de applicatie
RUN yarn build

# Start commando
CMD yarn medusa db:migrate && yarn start