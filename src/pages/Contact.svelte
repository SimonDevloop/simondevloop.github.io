<script lang="ts">
  const contacts = [
    { label: 'GitHub', href: 'https://github.com/SimonDevloop', text: '@SimonDevloop' },
    { label: 'Twitter', href: 'https://x.com/simonthecollie', text: '@simonthecollie' },
  ]
</script>

<section class="contact">
  <h1 class="title">Contact</h1>
  <div class="content">
    <p>Feel free to reach out. I'm always open to new opportunities and conversations.</p>
    <ul class="contactList">
      {#each contacts as { label, href, text }}
        <li>
          <span class="label">{label}</span>
          <a href={href} target="_blank" rel="noopener noreferrer">{text}</a>
        </li>
      {/each}
    </ul>
  </div>
</section>

<style>
  .contact {
    padding-top: 24px;
  }

  .title {
    font-size: 28px;
    font-weight: 600;
    color: #ffffff;
    letter-spacing: -0.03em;
    margin-bottom: 24px;
  }

  .content {
    font-size: 16px;
    line-height: 1.8;
    color: rgba(255, 255, 255, 0.65);

    & p {
      margin-bottom: 20px;
    }
  }

  .contactList {
    padding-left: 0;
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 12px;

    & li {
      display: flex;
      align-items: center;
      gap: 16px;
      padding: 16px 20px;
      background-color: rgba(255, 255, 255, 0.03);
      border: 1px solid rgba(255, 255, 255, 0.06);
      border-radius: 8px;
      font-size: 15px;
      color: rgba(255, 255, 255, 0.75);
      transition: border-color 0.2s ease, background-color 0.2s ease;

      &:hover {
        background-color: rgba(255, 255, 255, 0.05);
        border-color: rgba(255, 255, 255, 0.1);
      }

      &::before {
        content: '// ';
        font-size: 13px;
        color: rgba(255, 255, 255, 0.2);
      }
    }
  }

  .label {
    font-weight: 500;
    color: rgba(255, 255, 255, 0.4);
    white-space: nowrap;
  }

  .contactList a {
    color: rgba(255, 255, 255, 0.85);
    text-decoration: underline;
    text-underline-offset: 2px;
    transition: color 0.2s ease;

    &:hover {
      color: #ffffff;
    }
  }
</style>
