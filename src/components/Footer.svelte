<footer class="footer">
  <p>&copy; {new Date().getFullYear()} Simon Collie Grayson. All rights reserved.</p>
  <p>Licensed under the <a href="https://opensource.org/licenses/MIT" target="_blank" rel="noopener noreferrer">MIT License</a></p>
</footer>

<style>
  .footer {
    text-align: center;
    padding: 32px 24px;
    border-top: 1px solid rgba(255, 255, 255, 0.06);
    font-size: 13px;
    color: rgba(255, 255, 255, 0.35);

    & p + p {
      margin-top: 4px;
    }

    & a {
      color: rgba(255, 255, 255, 0.5);
      transition: color 0.2s ease;

      &:hover {
        color: rgba(255, 255, 255, 0.8);
        text-decoration: underline;
      }
    }
  }
</style>
