AI Market Research Agent with Gemini and Vercel AI SDKThis project is a Node.js-based autonomous agent that performs market research using the Google Gemini API via the Vercel AI SDK. It automates the process of gathering web data, extracting structured information, generating charts, and compiling a professional PDF report.FeaturesAutomated Web Research: Uses Gemini with the Google Search tool to find up-to-date market trend information.Structured Data Extraction: Leverages generateObject and Zod to reliably parse unstructured text into clean JSON for charts.Dynamic Chart Generation: Integrates Chart.js to create data visualizations on the fly.PDF Report Generation: Uses Puppeteer to render the final HTML report into a polished, multi-page PDF document.PrerequisitesBefore you begin, ensure you have the following installed and configured:Node.js: Version 18 or later.Package Manager: npm, pnpm, or yarn.Gemini API Key: You can get a free API key from Google AI Studio.🚀 Getting StartedFollow these steps to set up and run the project locally.1. Clone or Create the ProjectFirst, create a new directory for your project and navigate into it.mkdir market-trend-agent
cd market-trend-agent
npm init -y
2. Install DependenciesInstall the Vercel AI SDK, the Google Generative AI provider, and other necessary dependencies in one go.# Install core AI, validation, rendering, and charting libraries
npm install ai @ai-sdk/google zod puppeteer chart.js

# Install TypeScript and developer dependencies
npm install -D typescript @types/node @types/chart.js tsx

# Initialize a TypeScript configuration file
npx tsc --init
Note on Puppeteer: The puppeteer package will download a compatible version of the Chromium browser during installation. Your package manager may ask for approval to run the download script; please approve it.3. Configure TypeScript (tsconfig.json)After running npx tsc --init, a tsconfig.json file will be created. To prevent a common compiler error with modern modules, open this file and comment out the following line:// "verbatimModuleSyntax": true,
4. Configure Your API KeyThe application needs your Gemini API key to function. Set it as an environment variable named GOOGLE_GENERATIVE_AI_API_KEY.For macOS / Linux:export GOOGLE_GENERATIVE_AI_API_KEY="YOUR_API_KEY_HERE"
For Windows (PowerShell):$env:GOOGLE_GENERATIVE_AI_API_KEY="YOUR_API_KEY_HERE"
5. Create the Application FileCreate a new file named main.ts in your project's root directory and paste the complete code from the project source into it.⚡ Running the ApplicationTo run the agent, execute the following command in your terminal. This command will first compile the TypeScript file into JavaScript and then run the resulting code.npx tsc && node main.js
You will see log messages in your terminal as the script completes each step:1. Researching market trends...
✅ Market trends found.
2. Extracting chart data...
✅ 2 chart configurations generated.
3. Generating HTML report...
✅ HTML report generated.
4. Rendering PDF...

📄 Report generated successfully: report.pdf
📄 OutputOnce the script finishes, a file named report.pdf will be created in your project directory, containing the complete market analysis with text and charts.LicenseThis project is licensed under the MIT License. See the LICENSE file for details.
