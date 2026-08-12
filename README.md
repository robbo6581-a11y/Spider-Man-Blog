<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>WebHead | Spider-Man Blog</title>

    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: Arial, Helvetica, sans-serif;
            background: #080808;
            color: white;
            min-height: 100vh;
        }

        /* HEADER */
        header {
            background: linear-gradient(135deg, #b40000, #e00000);
            padding: 20px 7%;
            display: flex;
            align-items: center;
            justify-content: space-between;
            box-shadow: 0 4px 20px rgba(255, 0, 0, 0.35);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            font-size: 30px;
            font-weight: 900;
            letter-spacing: 2px;
        }

        .logo span {
            color: #111;
        }

        nav a {
            color: white;
            text-decoration: none;
            margin-left: 25px;
            font-weight: bold;
        }

        nav a:hover {
            color: #111;
        }

        /* HERO */
        .hero {
            min-height: 430px;
            padding: 70px 8%;
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 40px;
            background:
                radial-gradient(circle at 80% 30%, #e00000 0%, transparent 35%),
                linear-gradient(135deg, #050505, #101a35);
        }

        .hero-text {
            max-width: 650px;
        }

        .hero h1 {
            font-size: clamp(45px, 7vw, 85px);
            line-height: 0.95;
            margin-bottom: 25px;
        }

        .hero h1 span {
            color: #e00000;
        }

        .hero p {
            color: #ccc;
            font-size: 19px;
            line-height: 1.6;
            margin-bottom: 30px;
        }

        .hero-button {
            display: inline-block;
            background: #e00000;
            color: white;
            padding: 15px 25px;
            border-radius: 8px;
            text-decoration: none;
            font-weight: bold;
            transition: 0.2s;
        }

        .hero-button:hover {
            background: #ff2929;
            transform: translateY(-2px);
        }

        .spider {
            font-size: 170px;
            filter: drop-shadow(0 0 30px red);
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }

            50% {
                transform: translateY(-15px);
            }
        }

        /* MAIN */
        main {
            width: 90%;
            max-width: 1200px;
            margin: 50px auto;
        }

        .section-title {
            font-size: 36px;
            margin-bottom: 25px;
        }

        .section-title span {
            color: #e00000;
        }

        /* SEARCH */
        .search-box {
            width: 100%;
            padding: 15px;
            background: #151515;
            border: 1px solid #333;
            color: white;
            border-radius: 8px;
            font-size: 16px;
            margin-bottom: 35px;
        }

        .search-box:focus {
            outline: 2px solid #e00000;
        }

        /* POSTS */
        .posts {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
        }

        .post {
            background: #141414;
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid #292929;
            transition: 0.25s;
        }

        .post:hover {
            transform: translateY(-5px);
            border-color: #e00000;
            box-shadow: 0 10px 30px rgba(230, 0, 0, 0.2);
        }

        .post-image {
            width: 100%;
            height: 220px;
            object-fit: cover;
            background: #222;
        }

        .post-content {
            padding: 22px;
        }

        .post-date {
            color: #e00000;
            font-size: 13px;
            font-weight: bold;
            margin-bottom: 8px;
        }

        .post h3 {
            font-size: 24px;
            margin-bottom: 12px;
        }

        .post p {
            color: #bbb;
            line-height: 1.6;
            white-space: pre-wrap;
        }

        .post-actions {
            display: flex;
            gap: 8px;
            margin-top: 20px;
            flex-wrap: wrap;
        }

        button {
            border: none;
            cursor: pointer;
            font-weight: bold;
            border-radius: 6px;
            padding: 10px 14px;
        }

        .like-btn {
            background: #222;
            color: white;
        }

        .like-btn:hover {
            background: #333;
        }

        .edit-btn {
            background: #164d9b;
            color: white;
        }

        .delete-btn {
            background: #a00000;
            color: white;
        }

        /* CREATE POST */
        .create-section {
            margin-top: 70px;
            background: #111;
            border: 1px solid #292929;
            border-radius: 15px;
            padding: 30px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            font-weight: bold;
            margin-bottom: 8px;
        }

        input,
        textarea {
            width: 100%;
            background: #1c1c1c;
            border: 1px solid #444;
            color: white;
            padding: 14px;
            border-radius: 7px;
            font-size: 16px;
        }

        input:focus,
        textarea:focus {
            outline: 2px solid #e00000;
        }

        textarea {
            min-height: 180px;
            resize: vertical;
        }

        .image-preview {
            margin-top: 15px;
            max-width: 300px;
            max-height: 200px;
            display: none;
            border-radius: 8px;
            object-fit: cover;
        }

        .publish-btn {
            background: #e00000;
            color: white;
            padding: 14px 25px;
            font-size: 16px;
        }

        .publish-btn:hover {
            background: #ff2525;
        }

        .cancel-btn {
            background: #333;
            color: white;
            padding: 14px 25px;
            font-size: 16px;
            display: none;
            margin-left: 8px;
        }

        /* EMPTY */
        .empty {
            text-align: center;
            padding: 60px 20px;
            background: #111;
            border-radius: 12px;
            color: #aaa;
        }

        /* FOOTER */
        footer {
            margin-top: 80px;
            background: #050505;
            border-top: 1px solid #222;
            text-align: center;
            padding: 35px;
            color: #888;
        }

        footer strong {
            color: #e00000;
        }

        /* MOBILE */
        @media (max-width: 700px) {
            header {
                flex-direction: column;
                gap: 12px;
            }

            nav a {
                margin: 0 8px;
            }

            .hero {
                text-align: center;
                justify-content: center;
            }

            .spider {
                display: none;
            }

            .create-section {
                padding: 20px;
            }
        }
    </style>
</head>

<body>

<header>
    <div class="logo">WEB<span>HEAD</span> 🕷️</div>

    <nav>
        <a href="#posts">Posts</a>
        <a href="#create">Create Post</a>
    </nav>
</header>

<section class="hero">
    <div class="hero-text">
        <h1>
            THE <span>SPIDER-MAN</span><br>
            BLOG
        </h1>

        <p>
            Your place for Spider-Man news, theories, comic discussions,
            movie reviews, fan art and everything web-slinging.
        </p>

        <a href="#create" class="hero-button">
            Create a Post 🕷️
        </a>
    </div>

    <div class="spider">
        🕷️
    </div>
</section>


<main>

    <!-- POSTS -->
    <section id="posts">
        <h2 class="section-title">
            Latest <span>Posts</span>
        </h2>

        <input
            type="text"
            id="search"
            class="search-box"
            placeholder="Search posts..."
        >

        <div id="postsContainer" class="posts"></div>
    </section>


    <!-- CREATE POST -->
    <section id="create" class="create-section">

        <h2 class="section-title">
            Create a <span>New Post</span>
        </h2>

        <form id="postForm">

            <div class="form-group">
                <label for="title">Post Title</label>

                <input
                    type="text"
                    id="title"
                    placeholder="Enter your post title..."
                    required
                >
            </div>


            <div class="form-group">
                <label for="content">Post Content</label>

                <textarea
                    id="content"
                    placeholder="Write your Spider-Man post..."
                    required
                ></textarea>
            </div>


            <div class="form-group">
                <label for="image">
                    Add an Image
                </label>

                <input
                    type="file"
                    id="image"
                    accept="image/*"
                >

                <img
                    id="imagePreview"
                    class="image-preview"
                    alt="Image preview"
                >
            </div>


            <button
                type="submit"
                class="publish-btn"
                id="publishButton"
            >
                Publish Post 🕷️
            </button>

            <button
                type="button"
                class="cancel-btn"
                id="cancelButton"
            >
                Cancel Edit
            </button>

        </form>

    </section>

</main>


<footer>
    <p>
        🕷️ <strong>WEBHEAD</strong> — A fan-made Spider-Man blog
    </p>
</footer>


<script>

    let posts = JSON.parse(
        localStorage.getItem("spidermanPosts")
    ) || [];

    let editingId = null;
    let selectedImage = "";


    /*
    ---------------------------
    IMAGE SELECTION
    ---------------------------
    */

    const imageInput =
        document.getElementById("image");

    const imagePreview =
        document.getElementById("imagePreview");


    imageInput.addEventListener("change", function () {

        const file = this.files[0];

        if (!file) return;

        const reader = new FileReader();

        reader.onload = function (event) {

            selectedImage = event.target.result;

            imagePreview.src = selectedImage;
            imagePreview.style.display = "block";

        };

        reader.readAsDataURL(file);

    });


    /*
    ---------------------------
    SAVE POSTS
    ---------------------------
    */

    function savePosts() {

        localStorage.setItem(
            "spidermanPosts",
            JSON.stringify(posts)
        );

    }


    /*
    ---------------------------
    DISPLAY POSTS
    ---------------------------
    */

    function displayPosts(searchTerm = "") {

        const container =
            document.getElementById("postsContainer");

        container.innerHTML = "";

        const filteredPosts = posts.filter(post => {

            return (
                post.title
                    .toLowerCase()
                    .includes(searchTerm.toLowerCase()) ||

                post.content
                    .toLowerCase()
                    .includes(searchTerm.toLowerCase())
            );

        });


        if (filteredPosts.length === 0) {

            container.innerHTML = `
                <div class="empty">
                    <h3>No posts found 🕷️</h3>
                    <p>Create your first Spider-Man post!</p>
                </div>
            `;

            return;
        }


        filteredPosts.forEach(post => {

            const article =
                document.createElement("article");

            article.className = "post";


            const imageHTML = post.image
                ? `<img
                        src="${post.image}"
                        class="post-image"
                        alt="${escapeHTML(post.title)}"
                   >`
                : `<div
                        class="post-image"
                        style="
                            display:flex;
                            align-items:center;
                            justify-content:center;
                            font-size:70px;
                        "
                   >
                        🕷️
                   </div>`;


            article.innerHTML = `

                ${imageHTML}

                <div class="post-content">

                    <div class="post-date">
                        ${post.date}
                    </div>

                    <h3>
                        ${escapeHTML(post.title)}
                    </h3>

                    <p>
                        ${escapeHTML(post.content)}
                    </p>

                    <div class="post-actions">

                        <button
                            class="like-btn"
                            onclick="likePost(${post.id})"
                        >
                            ❤️ ${post.likes}
                        </button>

                        <button
                            class="edit-btn"
                            onclick="editPost(${post.id})"
                        >
                            ✏️ Edit
                        </button>

                        <button
                            class="delete-btn"
                            onclick="deletePost(${post.id})"
                        >
                            🗑️ Delete
                        </button>

                    </div>

                </div>
            `;


            container.appendChild(article);

        });

    }


    /*
    ---------------------------
    CREATE / EDIT POST
    ---------------------------
    */

    document
        .getElementById("postForm")
        .addEventListener("submit", function(event) {

            event.preventDefault();


            const title =
                document.getElementById("title").value.trim();

            const content =
                document.getElementById("content").value.trim();


            if (!title || !content) {

                alert("Please enter a title and content.");

                return;
            }


            if (editingId !== null) {

                const post =
                    posts.find(p => p.id === editingId);


                post.title = title;
                post.content = content;


                if (selectedImage) {
                    post.image = selectedImage;
                }


                editingId = null;

                document.getElementById(
                    "publishButton"
                ).textContent = "Publish Post 🕷️";

                document.getElementById(
                    "cancelButton"
                ).style.display = "none";

            } else {

                const newPost = {

                    id: Date.now(),

                    title: title,

                    content: content,

                    image: selectedImage,

                    likes: 0,

                    date: new Date().toLocaleDateString(
                        "en-IE",
                        {
                            day: "numeric",
                            month: "long",
                            year: "numeric"
                        }
                    )

                };


                posts.unshift(newPost);

            }


            savePosts();

            displayPosts();

            this.reset();

            selectedImage = "";

            imagePreview.style.display = "none";

            imagePreview.src = "";

            window.location.hash = "posts";

        });


    /*
    ---------------------------
    LIKE POST
    ---------------------------
    */

    function likePost(id) {

        const post =
            posts.find(p => p.id === id);

        if (!post) return;

        post.likes++;

        savePosts();

        displayPosts(
            document.getElementById("search").value
        );

    }


    /*
    ---------------------------
    DELETE POST
    ---------------------------
    */

    function deletePost(id) {

        const confirmed =
            confirm("Delete this Spider-Man post?");

        if (!confirmed) return;


        posts = posts.filter(
            post => post.id !== id
        );

        savePosts();

        displayPosts();

    }


    /*
    ---------------------------
    EDIT POST
    ---------------------------
    */

    function editPost(id) {

        const post =
            posts.find(p => p.id === id);

        if (!post) return;


        editingId = id;


        document.getElementById(
            "title"
        ).value = post.title;


        document.getElementById(
            "content"
        ).value = post.content;


        selectedImage = post.image || "";


        if (post.image) {

            imagePreview.src = post.image;

            imagePreview.style.display = "block";

        }


        document.getElementById(
            "publishButton"
        ).textContent = "Save Changes 🕷️";


        document.getElementById(
            "cancelButton"
        ).style.display = "inline-block";


        document
            .getElementById("create")
            .scrollIntoView({
                behavior: "smooth"
            });

    }


    /*
    ---------------------------
    CANCEL EDIT
    ---------------------------
    */

    document
        .getElementById("cancelButton")
        .addEventListener("click", function() {

            editingId = null;

            document
                .getElementById("postForm")
                .reset();

            selectedImage = "";

            imagePreview.style.display = "none";

            imagePreview.src = "";

            document.getElementById(
                "publishButton"
            ).textContent = "Publish Post 🕷️";

            this.style.display = "none";

        });


    /*
    ---------------------------
    SEARCH
    ---------------------------
    */

    document
        .getElementById("search")
        .addEventListener("input", function() {

            displayPosts(this.value);

        });


    /*
    ---------------------------
    SECURITY
    ---------------------------
    */

    function escapeHTML(text) {

        const div =
            document.createElement("div");

        div.textContent = text;

        return div.innerHTML;

    }


    /*
    ---------------------------
    INITIAL LOAD
    ---------------------------
    */

    displayPosts();

</script>

</body>
</html>
