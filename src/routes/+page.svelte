<script>
  let text = "";

  const countWords = (str) => {
    return str.trim().length === 0
      ? 0
      : str.trim().split(/\s+/).length;
  };
</script>

<div class="bg-gray-900 text-white min-h-screen">
    <div class="text-center p-6">
        <h1 class="text-3xl font-bold">📝 Character & Word Counter</h1>
    </div>
    
    <div class="flex gap-6 p-6">
      <!-- Text area -->
      <textarea
        bind:value={text}
        placeholder="Type your text here..."
        rows="10"
        class="flex-1 p-3 border rounded resize-none bg-gray-800 border-gray-700 text-white"
      ></textarea>
    
      <!-- Stats -->
      <div class="w-64 p-4 border rounded bg-gray-700 border-gray-600">
        <h2 class="text-lg font-semibold mb-3">📊 Statistics</h2>
        <p><strong>Total characters:</strong> {text.length}</p>
        <p><strong>Without spaces:</strong> {text.replace(/\s/g, "").length}</p>
        <p><strong>Spaces:</strong> {(text.match(/\s/g) || []).length}</p>
        <p><strong>Words:</strong> {countWords(text)}</p>
      </div>
    </div>
</div>