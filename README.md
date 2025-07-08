
# Diff Digest

A real-time web application that transforms GitHub pull request diffs into dual-tone release notes using AI. Built with Next.js 15, streaming APIs, and OpenAI integration.

## What I Built

I created a sophisticated tool that:
- **Fetches merged PR diffs** from any GitHub repository via the GitHub API
- **Generates dual-tone release notes** using LLMs - technical notes for developers and user-friendly notes for marketing
- **Streams AI responses in real-time** for a smooth, responsive user experience
- **Handles complex edge cases** including network failures, malformed data, and API errors

## Technical Implementation

### Core Technologies
- **Next.js 15** with Edge Runtime for optimal performance
- **TypeScript** for type safety and better developer experience
- **OpenAI SDK** for LLM integration
- **@octokit/rest** for GitHub API interactions
- **Tailwind CSS** for responsive styling
- **React Hooks** for state management

### Key Features I Developed

#### 1. Smart API Design
Created a robust `/api/sample-diffs` endpoint that:
- Supports flexible repository selection via query parameters
- Implements pagination for large datasets
- Returns structured diff data with proper error handling
- Defaults to OpenAI's Node.js repository as a demo

#### 2. Prompt Engineering Excellence
Designed sophisticated prompts that instruct the LLM to:
- Generate concise, technical developer notes focusing on implementation details
- Create user-centric marketing notes highlighting benefits in simple language
- Maintain consistency across different types of code changes
- Handle various diff formats and edge cases

#### 3. Real-Time Streaming Architecture
Implemented live updates using:
- Client-side streaming consumption
- Chunk-by-chunk UI updates
- Graceful handling of stream interruptions
- Progress indicators for better UX

#### 4. Robust Error Handling
Built comprehensive error management for:
- Network failures and timeouts
- Malformed JSON responses
- API rate limiting
- LLM inconsistencies or refusals

## Getting Started

### Prerequisites
- Node.js 18+
- npm/pnpm/yarn
- GitHub Personal Access Token (optional, for higher rate limits)
- OpenAI API Key

### Installation

```bash
# Clone the repository
git clone https://github.com/nrao04/diff-digest.git
cd diff-digest

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env.local
```

### Environment Configuration

Create a `.env.local` file with:

```env
GITHUB_TOKEN=your_github_token_here      # Optional: Increases API rate limits
GITHUB_OWNER=your_preferred_owner        # Default: openai
GITHUB_REPO=your_preferred_repo          # Default: openai-node
OPENAI_API_KEY=your_openai_api_key      # Required for AI features
```

### Running the Application

```bash
npm run dev
# Open http://localhost:3000
```

## Design Decisions

### Why Streaming?
I chose to implement real-time streaming to provide immediate feedback to users. This creates a more engaging experience compared to traditional loading states, especially when processing multiple PRs.

### Dual-Tone Approach
Recognizing that different audiences need different information, I designed the system to generate two distinct note styles:
- **Developer Notes**: Technical, precise, implementation-focused
- **Marketing Notes**: Benefit-driven, accessible, user-focused

### Architecture Choices
- **Client Components**: Used for interactive elements requiring real-time updates
- **Edge Runtime**: Leveraged for optimal performance and global distribution
- **Modular Design**: Separated concerns for easy maintenance and testing

## Future Enhancements

I'm planning to add:
- **Tool-calling capabilities** to enrich streams with related issues and contributor information
- **State persistence** to maintain generated notes across page refreshes
- **Batch processing** for generating notes for multiple PRs simultaneously
- **Export functionality** for generated release notes in various formats
- **Custom prompt templates** for different use cases

## Performance Considerations

- Implemented efficient pagination to handle large repositories
- Used React hooks optimally to prevent unnecessary re-renders
- Designed API responses to minimize payload size
- Implemented proper caching strategies

## Contributing

This project demonstrates my approach to:
- Modern web application architecture
- AI/LLM integration
- Real-time data processing
- User experience design
- Error handling and edge cases

Feel free to explore the codebase to see my coding style and problem-solving approach!

## License

MIT License - feel free to use this code as inspiration for your own projects!

---

Built by [nrao04](https://github.com/nrao04) - Turning complex diffs into clear, actionable release notes.
