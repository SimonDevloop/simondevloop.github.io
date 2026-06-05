<section class="about">
  <h1 class="title">About Me</h1>
  <div class="content">
    <p>In the background, I'm constantly learning and growing. My focus areas include:</p>
    <ul class="focusList">
      <li>Learning how to do software development</li>
      <li>Learning new programming languages</li>
      <li>Learning how to lead a team</li>
    </ul>
    
    <hr/>
    
    <p>
      I've never really learnt on how to draw art myself. My close friend
      <a href="https://codedave.pages.dev/" target="_blank" rel="noopener noreferrer">Daveberry</a>
      always draws for me. (Thanks, by the way!)
    </p>
  </div>
</section>

<style>
  .about {
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

    hr {
      margin: 20px 0;
      border: none;
      background-color: rgba(255, 255, 255, 0.15);
      border-radius: 5px;
      padding: 1.25px;
    }
  }

  .focusList {
    margin-top: 20px;
    padding-left: 0;
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 12px;

    & li {
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
</style>
