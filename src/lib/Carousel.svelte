<script  lang="ts">
    type DocumentType = {
        title: string
        src: string
    }
    export let documents: DocumentType[]
  </script>
  
  
  
  <ul>
    
    {#each documents  as { title,src }}
    <li>
        <doc {title} {src} alt={title} />
    </li>
      
    {/each}
  </ul>