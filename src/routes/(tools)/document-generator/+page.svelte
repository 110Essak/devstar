<script>
    import { onMount } from 'svelte';
    let documents = [
      { title: 'Complaint Form', src: '/doc01.png' },
      { title: 'Intake Form', src: '/doc02.png' },
      { title: 'Leave Request Form', src: '/doc03.png' },
      { title: 'Reservation Form', src: 'https://picsum.photos/600' },
      { title: 'Check-in Form', src: 'https://picsum.photos/600' }
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
    <div class="w-full h-full text-black dark:text-white flex flex-col">
      <h1 class="text-center">Devstar Document Templates Module</h1>
      <div class="flex">
        <div class="w-1/5 border border-yellow-100">
          <nav>
            <ul class="list-none p-2">
              <li class="p-2">1</li>
              <li class="p-2">2</li>
              <li class="p-2">3</li>
              <li class="p-2">4</li>
              <li class="p-2">5</li>
            </ul>
          </nav>
        </div>
        <div class="w-3/5 flex flex-col gap-10 border border-yellow-100 items-center justify-center">
          <div class="carousel flex flex-col items-center justify-center w-full">
            <div class="flex items-center justify-center w-full">
              <button on:click={prev} class="bg-blue-500 text-white p-2 rounded hover:bg-blue-700 transition duration-300">Prev</button>
              <img 
                src={documents[currentIndex].src} 
                alt={documents[currentIndex].title} 
                class="document-viewer mx-4"
              />
              <button on:click={next} class="bg-blue-500 text-white p-2 rounded hover:bg-blue-700 transition duration-300">Next</button>
            </div>
            <a href={documents[currentIndex].src} download={documents[currentIndex].title}
              class="download-btn mt-4">Download
              <i class="fa fa-download"></i>
            </a>
          </div>
        </div>
        <div class="w-1/5 border border-yellow-100">Right Side Search bar with some text</div>
      </div>
    </div>
  </div>
  
  <style>
    .carousel {
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
    }
  
    .document-viewer {
      max-width: 100%;
      max-height: 400px;
      object-fit: contain;
    }
  
    .download-btn {
      padding: 10px 20px;
      background-color: #007bff;
      color: white;
      border-radius: 5px;
      text-decoration: none;
    }
  
    .download-btn:hover {
      background-color: #0056b3;
    }
  </style>