


# [How to Deploy an Astro Website to AWS](https://www.youtube.com/watch?v=SXkZEVFS9d0)
```
PROJECT:

npm create astro@latest astro-deploy-aws

vi astro.config.mjs   # change 'output:' to 'server'
--
// @ts-check
import { defineConfig } from 'astro/config';

// https://astro.build/config
export default defineConfig({
  output: 'server'
  adapter: amplify()
});

--

# install AWS Amplify
npm install astro-aws-amplify

```

#############
# AWS Console
#
- open AWS Amplify
- DeployAnApp   # follow guidance
- App Settings -> 'Edit YML'  # to add Amplify settings
--
version: 1
frontend:
  phases:
    preBuild:
      commands:
        - npm ci --cache .npm --prefer-offline
    build:
      commands:
        - npm run build
        - mv node_modules ./.amplify-hosting/compute/default
  artifacts:
    baseDirectory: .amplify-hosting
    files:
      - '**/*'
  cache:
    paths:
      - .npm/**/*
--
- Environmental Variables
--
Key: _CUSTOM_IMAGE
Value: amplify:al2023
--

- NEXT -> Save & Deploy



