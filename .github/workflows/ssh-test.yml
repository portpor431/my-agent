name: SSH Test

on:
  workflow_dispatch:

jobs:
  ssh-test:
    runs-on: ubuntu-latest

    steps:
      - name: Manual tmate setup
        run: |
          set -x
          sudo apt-get update
          sudo apt-get install -y tmate
          ssh-keygen -t ed25519 -f ~/.ssh/id_ed25519 -N "" -q
          tmate -S /tmp/tmate.sock new-session -d
          tmate -S /tmp/tmate.sock wait tmate-ready
          echo "===== CONNECTION STRING ====="
          tmate -S /tmp/tmate.sock display -p '#{tmate_ssh}'
          echo "=============================="
          sleep 3000
