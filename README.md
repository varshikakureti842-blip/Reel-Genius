# Reel-Genius — Free Video Generator

An n8n automation that turns a topic into a short video using AI-generated scripts, stock footage, text-to-speech narration, and automated rendering.

## How it works

1. **Form submission** collects a topic and requested number of scenes.
2. **Gemini Script** generates a title, narration, and stock-footage search keywords for each scene.
3. **Coverr Video Search** finds stock clips, and **Pick Clip** selects usable video URLs.
4. **Collect Clips** builds the video timeline and combines the narration.
5. **Gemini TTS** generates the voiceover audio.
6. **Shotstack** ingests the voiceover and renders the final MP4.
7. **Return Video Link** returns the render status and video URL.

## Requirements

- n8n
- Google Gemini API access for text generation and text-to-speech
- Coverr API access
- Shotstack API access for the Ingest and Edit APIs

## Import and configure

1. Download `workflow/Free-Video-Generator.json`.
2. In n8n, select **Workflows → Import from File**.
3. Configure the API-key placeholders in the imported workflow:
   - Gemini Script and Gemini TTS: `YOUR_GEMINI_API_KEY`
   - Coverr Video Search: `YOUR_COVERR_API_KEY`
   - Shotstack request, source-check, render, and render-status nodes: `YOUR_SHOTSTACK_API_KEY`
4. Save the workflow and test it with the form trigger.

## Security

The workflow export in this repository has had the API-key values replaced with placeholders. Do not commit real API keys, access tokens, webhook secrets, or personal execution data to a public repository. For production, prefer n8n credentials or a secrets manager over hardcoding secrets in node parameters.

If any key was previously exposed, revoke or rotate it with the provider even if it has since been removed from the repository.

## Notes

This repository contains the workflow export and setup instructions; it does not include provider accounts or API credentials. External API behavior, model availability, quotas, and pricing can change.

## License

No license is currently specified. Add a license file if you want to define how others may use, modify, or redistribute this project.
