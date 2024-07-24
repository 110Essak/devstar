<script>
    let documents = [
      { title: 'Template 1', src: 'https://picsum.photos/seed/picsum/200/300', description: 'A brief description of Template 1.' },
      { title: 'Template 2', src: 'https://picsum.photos/seed/picsum/200/300', description: 'A brief description of Template 2.' },
      { title: 'Template 3', src: 'https://picsum.photos/seed/picsum/200/300', description: 'A brief description of Template 3.' }
    ];
    let currentIndex = 0;
  
    function next() {
      currentIndex = (currentIndex + 1) % documents.length;
    }
  
    function prev() {
      currentIndex = (currentIndex - 1 + documents.length) % documents.length;
    }
  </script>
  
  <div class="card gap-16 items-center mx-auto max-w-screen-xl lg:grid lg:grid-cols-1 overflow-hidden rounded-lg">
    <div class="w-full h-full dark:text-white flex flex-col">
      <h1 class="text-center text-2xl font-bold mb-4">Devstar Document Templates Module</h1>
      <div class="flex">
        <!-- Left Sidebar -->
        <div class="w-[15%] border border-yellow-100 flex flex-col items-center">
          <nav>
            <ul>
              <li><button class="nav-btn">1</button></li>
              <li><button class="nav-btn">2</button></li>
              <li><button class="nav-btn">3</button></li>
              <li><button class="nav-btn">4</button></li>
              <li><button class="nav-btn">5</button></li>
            </ul>
          </nav>
        </div>
  
        <!-- Carousel Section -->
        <div class="w-[70%] flex flex-col gap-10 border border-yellow-100">
          <section class="template-section">
            <h2 class="text-xl font-bold mb-6 text-gray-800">Templates</h2>
            <div class="carousel flex overflow-x-auto gap-4">
              {#each documents as doc, index}
                <div class="template-card flex flex-col items-center relative">
                  <div class="group relative w-48 h-60 rounded-lg overflow-hidden bg-white shadow-lg hover:shadow-xl transition duration-300 ease-in-out transform hover:-translate-y-1">
                    <img class="w-full h-full object-cover group-hover:opacity-50 transition duration-300 ease-in-out" src={doc.src} alt={doc.title}>
                    <div class="absolute inset-0 px-4 py-2 bottom-0 opacity-0 group-hover:opacity-100 transition duration-300 ease-in-out bg-gradient-to-b from-gray-900 to-transparent">
                      <h3 class="text-lg font-bold text-white mb-2">{doc.title}</h3>
                      <p class="text-gray-300">{doc.description}</p>
                    </div>
                  </div>
                  <a href={doc.src} download={doc.title} class="download-btn mt-4 flex items-center" aria-label="Download Template {doc.title}">
                    Download <i class="fa fa-download ml-2"></i>
                  </a>
                </div>
              {/each}
            </div>
          </section>
        </div>
  
        <!-- Right Sidebar -->
        <div class="w-[15%] border border-yellow-100 flex flex-col items-center">
          <div class="search-bar mt-4">
            <input type="text" placeholder="Search..." class="w-full p-2 border rounded" aria-label="Search Templates"/>
          </div>
        </div>
      </div>
    </div>
  </div>
  
  <style>
    .template-section {
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    .carousel {
      display: flex;
      align-items: center;
    }
    .template-card {
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-bottom: 1rem;
      position: relative;
    }
    .group {
      width: 200px;
      height: 300px;
    }
    .carousel-button {
      padding: 0.5rem 1rem;
      background-color: #1f2937;
      color: #fff;
      border-radius: 0.25rem;
      transition: background-color 0.3s ease-in-out;
    }
    .carousel-button:hover {
      background-color: #374151;
    }
    .nav-btn {
      padding: 0.5rem;
      background: none;
      border: none;
      cursor: pointer;
      color: #1f2937;
    }
    .nav-btn:hover {
      background-color: #f0f0f0;
    }
    .search-bar {
      margin-top: 1rem;
    }
    .download-btn {
      padding: 10px 20px;
      background-color: #007bff;
      color: white;
      border-radius: 5px;
      text-decoration: none;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .download-btn:hover {
      background-color: #0056b3;
    }
  </style>