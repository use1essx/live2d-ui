# Deploy Live2D Frontend to Vercel

## Quick Deployment Steps

### Option 1: Deploy via Vercel CLI (Recommended)

1. **Install Vercel CLI** (if not already installed):
```bash
npm install -g vercel
```

2. **Navigate to the frontend directory**:
```bash
cd /workspaces/fyp2526-use1essx/healthcare_ai_live2d_unified/src/web/live2d/frontend
```

3. **Deploy**:
```bash
vercel
```

Follow the prompts:
- Login to your Vercel account
- Set up and deploy
- Choose project name (e.g., `live2d-ui-test`)

4. **Production deployment** (optional):
```bash
vercel --prod
```

### Option 2: Deploy via Vercel Dashboard

1. Go to [vercel.com](https://vercel.com)
2. Click "Add New Project"
3. Import your Git repository OR upload this folder directly
4. Set the **Root Directory** to: `healthcare_ai_live2d_unified/src/web/live2d/frontend`
5. Click "Deploy"

## What Works in UI-Only Mode

✅ **Working:**
- Live2D character display and animations
- UI layout and design
- Button interactions
- Chat message display
- Voice button UI
- Profile modal UI
- Auth UI components

⚠️ **Limited/Mock (Expected):**
- Backend API calls (will show errors - this is normal for UI testing)
- User authentication
- Chat responses (no backend)
- Voice recording (browser permission still works)

## Testing the UI

Once deployed, you can test:
- Visual design and layout
- Live2D character rendering
- UI responsiveness
- Button states and interactions
- Modal displays
- Chat message styling
- Input field behaviors

## Environment Notes

The current `index.html` has the API baseURL set to:
```javascript
this.baseUrl = 'http://localhost:8000';
```

For UI testing, this will simply fail gracefully and show connection errors, which is fine. The UI itself will still render and you can see all the visual components.

## Optional: Mock Backend

If you want to see the chat working without a real backend, you could:
1. Comment out the real API calls in the JavaScript
2. Add mock responses
3. Test the full UI flow with fake data

But for pure UI testing, the current setup is sufficient!

## Vercel Configuration

The `vercel.json` file configures:
- URL rewrites for clean routing
- CORS headers for API calls (when backend is connected)
- Static file serving

## Next Steps After UI Testing

Once you're happy with the UI:
1. Deploy the backend API (FastAPI) to a service like Railway, Render, or Vercel Serverless
2. Update the `baseUrl` in `index.html` to point to your deployed backend
3. Redeploy the frontend with the updated API URL

