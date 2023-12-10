<script>
    const projects = [
      {
        name: 'Project 1',
        description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec euismod, nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl',
        link: 'https://www.google.com',
      },
      {
        name: 'Project 2',
        description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec euismod, nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl',
        link: 'https://www.google.com',
      },
      {
        name: 'Project 3',
        description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec euismod, nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl',
        link: 'https://www.google.com',
      },
      {
        name: 'Project 4',
        description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec euismod, nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl nisl vitae aliquam ultricies, nunc nisl ultricies nunc, vitae aliquam nisl',
        link: 'https://www.google.com',
      }
    ];
</script>

<div class="index">
  {#each projects as project}
  <p>{project.name}</p>
  {/each}
</div>

<style>
   .index {
    font-family: 'Prompt-Regular';
    z-index: 1;
    border-radius: 4px;
    height: fit-content;
    width: 200px;
    display: flex;
    flex-direction: column;
    padding: 10px;
    background: #DDEC5B;
  }
</style>