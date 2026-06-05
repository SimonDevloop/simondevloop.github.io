<script lang="ts">
  const description = `I'm a software engineer, and my dream is to become a police officer. Close friends with <a href="https://codedave.pages.dev/" target="_blank" rel="noopener noreferrer">Daveberry</a>, Ace, and Bramble.`

  const skills = [
    { name: 'Python Development', level: 'Advanced' },
    { name: 'Website Development', level: 'Advanced' },
    { name: 'Software Development', level: 'Learning' },
  ]
</script>

<section class="home">
  <img class="profileImage" src="images/simon collie grayson.png" alt="Simon Collie Grayson"/>
  <!-- <div class="profileImage">
    <span class="initials">SCG</span>
  </div> -->
  <h1 class="name">Simon Collie Grayson</h1>
  <p class="description">{@html description}</p>
  <div class="skills">
    <h2 class="skillsTitle">Skills</h2>
    {#each skills as { name, level }}
      <div class="skill">
        <span class="skillName">{name}</span>
        <span class="skillDivider"></span>
        <span class="skillLevel">{level}</span>
      </div>
    {/each}
  </div>
</section>

<style>
  .home {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    padding-top: 24px;
  }

  .profileImage {
    width: 128px;
    height: 128px;
    border-radius: 50%;
    background-color: rgba(255, 255, 255, 0.06);
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 24px;
    border: 1px solid rgba(255, 255, 255, 0.08);
  }

  /*.initials {
    font-size: 36px;
    font-weight: 600;
    color: rgba(255, 255, 255, 0.3);
    letter-spacing: 0.06em;
  }*/

  .name {
    font-size: 32px;
    font-weight: 600;
    letter-spacing: -0.03em;
    margin-bottom: 16px;
    color: #ffffff;
  }

  .description {
    font-size: 16px;
    line-height: 1.7;
    color: rgba(255, 255, 255, 0.65);
    max-width: 540px;

    :global(a) {
      color: rgba(255, 255, 255, 0.85);
      text-decoration: underline;
      text-underline-offset: 2px;
      transition: color 0.2s ease;

      &:hover {
        color: #ffffff;
      }
    }
  }

  .skills {
    margin-top: 48px;
    width: 100%;
    max-width: 400px;
  }

  .skillsTitle {
    font-size: 13px;
    font-weight: 500;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: rgba(255, 255, 255, 0.3);
    margin-bottom: 16px;
  }

  .skill {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 12px 0;
    border-bottom: 1px solid rgba(255, 255, 255, 0.06);

    &:last-child {
      border-bottom: none;
    }
  }

  .skillName {
    font-size: 15px;
    color: rgba(255, 255, 255, 0.8);
  }

  .skillDivider {
    flex: 1;
    margin: 0 16px;
    border-bottom: 1px dotted rgba(255, 255, 255, 0.1);
  }

  .skillLevel {
    font-size: 14px;
    font-weight: 500;
    color: rgba(255, 255, 255, 0.45);
    flex-shrink: 0;
  }
</style>
