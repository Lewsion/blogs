# Contributing to Lewsion Blog & Documentation

We welcome and appreciate all contributions to our blog. Whether you're fixing a typo, improving an existing article, or writing a new one, your help is valuable to us. To ensure a smooth process, please read through these guidelines.

## How to Contribute

There are several ways you can contribute:

* **Reporting Issues:** If you find a typo, a factual error, or a broken link, please [open an issue](https://github.com/lewsion/blogs/issues).
* **Suggesting Enhancements:** If you have an idea for a new topic or a way to improve the blog, feel free to open an issue to discuss it.
* **Submitting Pull Requests:** If you want to contribute directly, you can do so by submitting a pull request.

## Submitting a Pull Request

1. **Fork the repository** and create a new branch for your changes.
2. **Write your content.** We encourage you to share your knowledge professionally. Ensure your content is well-researched, accurate, and clearly written.
3. **Add yourself as an author.** If you are a new contributor, please add your information to the `_data/authors.yml` file. You can follow the existing format:

    ```yaml
    your_username:
      name: Your Name
      twitter: your_twitter_handle (optional)
      url: your_github_profile_url (optional)
    ```

4. **Create a new post.** Create a new Markdown file in the `_posts` directory. The filename should follow the format `YYYY-MM-DD-your-post-title.md`.

5. **Add the front matter.** At the beginning of your post, include the following front matter:

    ```yaml
    ---
    title: Your Post Title
    date: YYYY-MM-DD HH:MM:SS +/-TTTT
    author: your_username
    categories: [Main Category, Sub Category]
    tags: [tag1, tag2]
    ---
    ```

6. **Submit your pull request.** Once you are ready, submit your pull request for review.

## Style Guide

* **Language:** Please write in clear and concise English.
* **Formatting:** Use Markdown for formatting. Keep the formatting clean and simple.
* **Professionalism:** We aim to provide high-quality, professional content. Please ensure your contributions meet this standard.

Thank you for your interest in contributing to our blog!
