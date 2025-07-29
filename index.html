// Import necessary libraries from CDN
import React, { useState, useMemo } from 'https://esm.sh/react@18.2.0';
import ReactDOM from 'https://esm.sh/react-dom@18.2.0/client';
import { GoogleGenerativeAI } from 'https://esm.sh/@google/generative-ai';

// --- HELPER COMPONENTS ---

const parseURLs = (text) => {
    const urlRegex = /(https?:\/\/[^\s,.)]+)/g;
    return text.split(urlRegex).map((part, index) => {
        if (part.match(urlRegex)) {
            return <a href={part} key={index} target="_blank" rel="noopener noreferrer" className="text-sky-400 underline hover:text-sky-300 transition-colors break-all">{part}</a>;
        }
        return part;
    });
};

const Header = () => (
    <header className="text-center p-4">
        <div className="flex items-center justify-center gap-3">
            <svg xmlns="http://www.w3.org/2000/svg" className="h-8 w-8 text-slate-400" fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2"><path strokeLinecap="round" strokeLinejoin="round" d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z" /></svg>
            <h1 className="text-3xl font-bold text-slate-100">Corporate Report Finder</h1>
        </div>
        <p className="text-slate-400 mt-2">AI-powered analyst to find official corporate reports and documents.</p>
    </header>
);

const SearchForm = ({ onSearch, isLoading }) => {
    const [company, setCompany] = useState('');
    const [query, setQuery] = useState('');
    const suggestions = ['Find the latest Annual Report', 'Find the latest ESG or Sustainability Report', 'Latest quarterly earnings report', 'Company diversity and inclusion report'];

    const handleSubmit = (e) => {
        e.preventDefault();
        if (company && query) onSearch(company, query);
    };

    return (
        <div className="bg-slate-800/50 border border-slate-700 rounded-lg p-6 shadow-lg">
            <form onSubmit={handleSubmit} className="space-y-6">
                <div>
                    <label htmlFor="company" className="block text-sm font-medium text-slate-300 mb-1">Company Name or Website</label>
                    <input id="company" type="text" value={company} onChange={(e) => setCompany(e.target.value)} placeholder="e.g., Google or google.com" className="w-full bg-slate-700/50 border border-slate-600 rounded-md px-3 py-2 focus:ring-2 focus:ring-sky-500 focus:border-sky-500 outline-none transition" required />
                </div>
                <div>
                    <label htmlFor="query" className="block text-sm font-medium text-slate-300 mb-1">User Query</label>
                    <textarea id="query" value={query} onChange={(e) => setQuery(e.target.value)} placeholder="What document are you looking for?" className="w-full bg-slate-700/50 border border-slate-600 rounded-md px-3 py-2 h-24 focus:ring-2 focus:ring-sky-500 focus:border-sky-500 outline-none transition resize-none" required />
                </div>
                <div className="flex flex-wrap gap-2">{suggestions.map(s => <button key={s} type="button" onClick={() => setQuery(s)} className="text-xs bg-slate-700 hover:bg-slate-600 text-slate-300 px-3 py-1 rounded-full transition">{s}</button>)}</div>
                <div>
                    <button type="submit" disabled={!company || !query || isLoading} className="w-full flex items-center justify-center gap-2 bg-sky-600 hover:bg-sky-500 text-white font-bold py-2 px-4 rounded-md transition disabled:bg-slate-600 disabled:cursor-not-allowed">
                        {isLoading ? (
                            <><svg className="animate-spin -ml-1 mr-3 h-5 w-5 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"><circle className="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" strokeWidth="4"></circle><path className="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path></svg>Searching...</>
                        ) : (
                            <><svg xmlns="http://www.w3.org/2000/svg" className="h-5 w-5" viewBox="0 0 20 20" fill="currentColor"><path fillRule="evenodd" d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z" clipRule="evenodd" /></svg>Find Report</>
                        )}
                    </button>
                </div>
            </form>
        </div>
    );
};

const ResultsDisplay = ({ searchResult, isLoading, error }) => {
    if (isLoading) return <div className="flex justify-center items-center p-16"><svg className="animate-spin h-10 w-10 text-sky-500" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"><circle className="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" strokeWidth="4"></circle><path className="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path></svg></div>;
    if (error) return <div className="bg-red-900/50 border border-red-700 text-red-300 px-4 py-3 rounded-lg relative flex items-center gap-3 animate-fade-in" role="alert"><svg xmlns="http://www.w3.org/2000/svg" className="h-6 w-6 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2"><path strokeLinecap="round" strokeLinejoin="round" d="M12 8v4m0 4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" /></svg><div><strong className="font-bold">An error occurred: </strong><span className="block sm:inline">{error}</span></div></div>;
    if (!searchResult) return <div className="text-center p-16 text-slate-500"><svg xmlns="http://www.w3.org/2000/svg" className="mx-auto h-24 w-24" fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="1"><path strokeLinecap="round" strokeLinejoin="round" d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z" /></svg><p className="mt-4 text-lg">Ready for Research</p></div>;

    const { answer, sources } = searchResult;
    return (
        <div className="space-y-6">
            <div className="bg-slate-800/50 border border-slate-700 rounded-lg p-6 animate-fade-in"><h2 className="text-xl font-semibold text-slate-200 mb-3">Analyst Conclusion</h2><div className="text-slate-300 leading-relaxed whitespace-pre-wrap">{parseURLs(answer)}</div></div>
            {sources && sources.length > 0 && (
                <div className="bg-slate-800/50 border border-slate-700 rounded-lg p-6 animate-fade-in">
                    <h2 className="text-xl font-semibold text-slate-200 mb-4">Verified Sources</h2>
                    <ul className="space-y-3">{sources.map((source, index) => <li key={index} className="flex items-start gap-3"><svg xmlns="http://www.w3.org/2000/svg" className="h-5 w-5 text-sky-400 flex-shrink-0 mt-1" fill="none" viewBox="0 0 24 24" stroke="currentColor" strokeWidth="2"><path strokeLinecap="round" strokeLinejoin="round" d="M13.828 10.172a4 4 0 00-5.656 0l-4 4a4 4 0 105.656 5.656l1.102-1.101m-.758-4.899a4 4 0 005.656 0l4-4a4 4 0 00-5.656-5.656l-1.1 1.1" /></svg><a href={source.url} target="_blank" rel="noopener noreferrer" className="text-slate-300 hover:text-sky-400 transition underline-offset-4 hover:underline break-all">{source.title}</a></li>)}</ul>
                </div>
            )}
        </div>
    );
};

const Footer = () => <footer className="text-center py-6 mt-8"><p className="text-xs text-slate-500">Powered by Google Gemini. For research purposes only.</p></footer>;

const ApiKeyForm = ({ onKeySubmit }) => {
    const [localKey, setLocalKey] = useState('');
    const handleSubmit = (e) => {
        e.preventDefault();
        if (localKey.trim()) onKeySubmit(localKey.trim());
    };
    
    return (
         <div className="max-w-md mx-auto p-4 animate-fade-in">
            <div className="bg-slate-800/50 border border-slate-700 rounded-lg p-8 shadow-lg">
                <div className="text-center mb-6">
                    <h2 className="text-2xl font-bold text-slate-100">Enter API Key</h2>
                    <p className="text-slate-400 mt-2">Please provide your Google Gemini API key to continue.</p>
                </div>
                <form onSubmit={handleSubmit} className="space-y-4">
                    <div>
                        <label htmlFor="apiKey" className="block text-sm font-medium text-slate-300 mb-1">Gemini API Key</label>
                        <input id="apiKey" type="password" value={localKey} onChange={(e) => setLocalKey(e.target.value)} placeholder="Enter your key here" className="w-full bg-slate-700/50 border border-slate-600 rounded-md px-3 py-2 focus:ring-2 focus:ring-sky-500 focus:border-sky-500 outline-none transition" required />
                    </div>
                    <button type="submit" className="w-full flex items-center justify-center gap-2 bg-sky-600 hover:bg-sky-500 text-white font-bold py-2 px-4 rounded-md transition">Save and Continue</button>
                </form>
            </div>
         </div>
    );
};

const MainApp = ({ apiKey }) => {
    const [searchResult, setSearchResult] = useState(null);
    const [isLoading, setIsLoading] = useState(false);
    const [error, setError] = useState(null);
    const aiClient = useMemo(() => new GoogleGenerativeAI(apiKey), [apiKey]);

    const findReport = async (company, query) => {
        const model = aiClient.getGenerativeModel({
            model: "gemini-1.5-flash",
            tools: [{ "googleSearch": {} }],
        });
        const prompt = `You are a highly specialized research analyst. Your sole mission is to find official corporate reports based on user queries, with a critical emphasis on URL accuracy and validity. Objective: Find the document that best answers the user's query for the company/website: "${company}". User Query: "${query}". Execution Protocol: 1. Primary Target: Your main goal is to find a direct link to an official report document (ideally a PDF). Search in investor relations sections, sustainability pages, or newsrooms of the company's official website first. 2. Answer Formulation: Begin with a concise, one-sentence conclusion that directly answers the user's query. The URL you provide MUST be directly taken from the search results. 3. URL Integrity: You MUST validate that any URL you provide is functional and leads directly to the specified report or official page. Do NOT guess, alter, or construct URLs. 4. Contingency: If, after a thorough search, you cannot find any relevant report or dedicated webpage, you MUST state that clearly. 5. Grounding: Your entire response MUST be derived from the information retrieved via the search tool.`;
        try {
            const result = await model.generateContent(prompt);
            const response = result.response;
            const groundingMetadata = response.candidates?.[0]?.groundingMetadata;
            const sources = groundingMetadata?.groundingAttributions?.map(att => ({ title: att.web?.title || 'Untitled Source', url: att.web?.uri || '#' })) || [];
            return { answer: response.text(), sources };
        } catch (err) {
            console.error("Gemini API Error:", err);
            throw new Error(err.message || "An unknown error occurred. Check the console for details.");
        }
    };

    const handleSearch = async (company, query) => {
        setIsLoading(true);
        setError(null);
        setSearchResult(null);
        try {
            const result = await findReport(company, query);
            setSearchResult(result);
        } catch (err) {
            setError(err.message);
        } finally {
            setIsLoading(false);
        }
    };

    return (
        <div className="max-w-2xl mx-auto px-4 py-8 animate-fade-in">
            <Header />
            <main className="mt-8 space-y-8">
                <SearchForm onSearch={handleSearch} isLoading={isLoading} />
                <ResultsDisplay searchResult={searchResult} isLoading={isLoading} error={error} />
            </main>
            <Footer />
        </div>
    );
};

const App = () => {
    const [apiKey, setApiKey] = useState(null);
    if (!apiKey) return <ApiKeyForm onKeySubmit={setApiKey} />;
    return <MainApp apiKey={apiKey} />;
};

// Find the root DOM element and render the React App
const rootElement = document.getElementById('root');
const root = ReactDOM.createRoot(rootElement);
root.render(<App />);
