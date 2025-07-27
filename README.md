# CodeBloom-WCHL
AI-powered ideation platform for building real-world social impact projects.

import { useState } from 'react';

function App() {
  const [input, setInput] = useState('');
  const [idea, setIdea] = useState('');

  const generateIdea = () => {
    // Mock idea logic — can connect to real backend later
    const prompts = [
      `Build a website that teaches "${input}" using AI-driven flashcards.`,
      `Use AI to track and improve "${input}" habits.`,
      `Create a community platform based on "${input}" interests.`
    ];
    const randomIdea = prompts[Math.floor(Math.random() * prompts.length)];
    setIdea(randomIdea);
  };

  return (
    <div className="min-h-screen bg-gray-100 flex flex-col items-center justify-center p-4">
      <h1 className="text-4xl font-bold mb-4">CodeBloom AI 🌱</h1>
      <input
        type="text"
        placeholder="Enter a topic (e.g. coding, fitness)"
        value={input}
        onChange={(e) => setInput(e.target.value)}
        className="p-2 border border-gray-300 rounded mb-4 w-full max-w-md"
      />
      <button
        onClick={generateIdea}
        className="bg-blue-600 text-white px-4 py-2 rounded"
      >
        Generate Idea
      </button>
      {idea && (
        <p className="mt-6 text-lg text-gray-800 bg-white p-4 rounded shadow-md max-w-xl">
          💡 {idea}
        </p>
      )}
    </div>
  );
}

export default App;

