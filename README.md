- 👋 Hi, I’m @akv40803
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
akv40803/akv40803 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
name: DevInfra

on:
  push:
  pull_request_target:
    types: [opened, synchronize, reopened, ready_for_review, labeled]

# Declare default permissions as read only.
permissions:
  contents: read

jobs:
  assistant_to_the_branch_manager:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@2541b1294d2704b0964813337f33b291d3f8596b # tag=v3.0.2
        with:
          persist-credentials: false
      - uses: angular/dev-infra/github-actions/branch-manager@0c06b3d1a58ab12f4f9933efc78e33083d008d17
        with:
          angular-robot-key: ${{ secrets.ANGULAR_ROBOT_PRIVATE_KEY }}
