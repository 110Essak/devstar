<script>
    let slideContainer;
    let documents = [
        { title: 'Template 1', src: 'https://picsum.photos/seed/picsum/200/300', description: 'A brief description of Template 1.' },
        { title: 'Template 2', src: 'https://picsum.photos/seed/picsum/200/300', description: 'A brief description of Template 2.' },
        { title: 'Template 3', src: 'https://picsum.photos/seed/picsum/200/300', description: 'A brief description of Template 3.' }
    ];

    function scrollLeft() {
        slideContainer.scrollBy({
            left: -300,
            behavior: 'smooth'
        });
    }

    function scrollRight() {
        slideContainer.scrollBy({
            left: 300,
            behavior: 'smooth'
        });
    }
</script>

<div class="card gap-16 items-center mx-auto max-w-screen-xl lg:grid lg:grid-cols-1 overflow-hidden rounded-lg">
    <div class="w-full h-full dark:text-white flex flex-col">
        <h1 class="text-center">Devstar Document Templates Module</h1>
        <div class="flex">
            <div class="w-[15%] border border-yellow-100">
                Left Side Navbar
                <nav>
                    <ul>
                        <li>1</li>
                        <li>2</li>
                        <li>3</li>
                        <li>4</li>
                        <li>5</li>
                    </ul>
                </nav>
            </div>
            <div class="w-[70%] flex gap-10 border border-yellow-100 relative">
                <section class="template-section px-10 py-10 pt-5">
                    <h1 class="text-xl font-bold mb-6 text-gray-800">Templates</h1>
                    <div class="flex overflow-x-auto gap-4 relative">
                        <button on:click={scrollLeft} class="prev-btn absolute left-2 top-1/2 transform -translate-y-1/2 bg-blue-500 hover:bg-blue-700 text-white px-3 py-2 rounded-md z-10">Prev</button>
                        <div bind:this={slideContainer} class="flex overflow-hidden">
                            {#each documents as doc (doc.title)}
                            <div class="group relative w-54 h-70 rounded-lg overflow-hidden bg-gray-900 cursor-pointer shadow-lg hover:shadow-xl transition duration-300 ease-in-out transform hover:-translate-y-1 flex-shrink-0 mx-2">
                                <img class="w-full h-full object-cover group-hover:opacity-50 transition duration-300 ease-in-out" src={doc.src} alt={doc.title}>
                                <div class="absolute inset-0 px-4 py-2 bottom-0 opacity-0 group-hover:opacity-100 transition duration-300 ease-in-out bg-gradient-to-b from-gray-900 to-transparent">
                                    <h3 class="text-lg font-bold text-white mb-2">{doc.title}</h3>
                                    <p class="text-white">{doc.description}</p>
                                </div>
                                <div class="absolute inset-0 flex items-center justify-center opacity-0 group-hover:opacity-100 transition duration-300 ease-in-out">
                                    <div class="flex flex-col space-y-2">
                                        <button class="bg-blue-500 text-white px-4 py-2 rounded-md w-24 text-center">Edit</button>
                                        <button class="bg-green-500 text-white px-4 py-2 rounded-md w-24 text-center">PDF</button>
                                        <button class="bg-red-500 text-white px-4 py-2 rounded-md w-24 text-center">Word</button>
                                    </div>
                                </div>
                            </div>
                            {/each}
                        </div>
                        <button on:click={scrollRight} class="next-btn absolute right-2 top-1/2 transform -translate-y-1/2 bg-blue-500 hover:bg-blue-700 text-white px-3 py-2 rounded-md z-10">Next</button>
                    </div>
                </section>
            </div>
            <div class="w-[15%] border border-yellow-100">Right Side Search bar with some text</div>
        </div>
    </div>
</div>

<style>
    .prev-btn, .next-btn {
        background-color: #3b82f6; /* Blue color */
        color: white;
        border: none;
        cursor: pointer;
    }

    .prev-btn:hover, .next-btn:hover {
        background-color: #2563eb; /* Darker blue color for hover */
    }

    .prev-btn {
        left: 2%; /* Adjust this value as needed to move closer to the left edge */
    }

    .next-btn {
        right: 2%; /* Adjust this value as needed to move closer to the right edge */
    }
</style>
