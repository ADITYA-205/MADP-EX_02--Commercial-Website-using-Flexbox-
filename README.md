# Ex02 - Commercial Website

## Date:
*10-08-2025*

## AIM
To create a commercial website using CSS Flexbox.

## ALGORITHM

### STEP 1
Create an HTML file (`index.html`).

### STEP 2
Create a CSS file (`style.css`).

### STEP 3
Include a navigation bar with links to different sections.

### STEP 4
Add structured sections for **Homepage**, **Products / Services**, **About Us**, **Contact Details**, and **User Account**.

### STEP 5
Include social media links at the footer with copyright information.

### STEP 6
Define global styles for fonts, colors, and layout.

### STEP 7
Style the header, navigation bar, and sections.

### STEP 8
Use **Flexbox** for layout design.

### STEP 9
Add hover effects and transitions for interactivity.

### STEP 10
Add images and media.

### STEP 11
Use optimized images for a professional look.

### STEP 12
Open the HTML file in a browser to check layout and functionality.

### STEP 13
Fix styling issues and refine content placement.

### STEP 14
Deploy the website.

### STEP 15
Upload to **GitHub Pages** for free hosting.

## PROGRAM
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BrewMaster - Premium Coffee & Espresso Store</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Segoe UI', sans-serif; line-height: 1.6; color: #2c2c2c; background-color: #f6f2ed; }

        /* Navigation */
        .navbar {
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(8px);
            padding: 1rem 2rem;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: auto;
        }
        .logo { font-size: 1.8rem; font-weight: bold; color: #8B4513; }
        .nav-links { display: flex; gap: 1.5rem; list-style: none; }
        .nav-links a { text-decoration: none; color: #2c2c2c; font-weight: 500; transition: color 0.3s; }
        .nav-links a:hover { color: #8B4513; }
        .nav-cta {
            background: linear-gradient(135deg, #8B4513, #c49a6c);
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 25px;
            text-decoration: none;
            font-weight: bold;
            transition: transform 0.3s;
        }
        .nav-cta:hover { transform: translateY(-2px); }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #f4e1d2, #e6cbbf);
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding: 0 2rem;
        }
        .hero-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            max-width: 1200px;
            margin: auto;
            align-items: center;
        }
        .hero-content h1 {
            font-size: 3.2rem;
            font-weight: bold;
            color: #4b2e1e;
            margin-bottom: 1rem;
        }
        .hero-content .highlight { color: #8B4513; }
        .hero-content p { font-size: 1.2rem; margin-bottom: 2rem; color: #3f3f3f; }
        .hero-cta {
            background: linear-gradient(135deg, #8B4513, #c49a6c);
            color: white;
            padding: 1rem 2rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            transition: 0.3s;
        }
        .hero-cta:hover { transform: translateY(-3px); }

        .hero-visual { display: flex; justify-content: center; }
        .main-product img { width: 300px; border-radius: 20px; box-shadow: 0 8px 20px rgba(0,0,0,0.2); }

        /* Products Section */
        .products {
            padding: 5rem 2rem;
            background: #fff;
        }
        .products-container { max-width: 1200px; margin: auto; }
        .products h2 { text-align: center; font-size: 2.5rem; color: #4b2e1e; margin-bottom: 3rem; }
        .products-flex-container {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            justify-content: center;
        }
        .product-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 8px 20px rgba(0,0,0,0.1);
            max-width: 320px;
            transition: transform 0.3s;
        }
        .product-card:hover { transform: translateY(-8px); }
        .product-image { height: 200px; display: flex; align-items: center; justify-content: center; background: #f6f2ed; }
        .product-image img { max-height: 100%; transition: transform 0.3s; }
        .product-card:hover img { transform: scale(1.05); }
        .product-info { padding: 1.5rem; }
        .product-info h3 { color: #4b2e1e; font-size: 1.4rem; margin-bottom: 0.5rem; }
        .product-info p { color: #555; font-size: 0.95rem; margin-bottom: 1rem; }
        .product-details {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
        }
        .price { font-size: 1.3rem; font-weight: bold; color: #8B4513; }
        .caffeine { background: #d6ccc2; padding: 0.3rem 0.6rem; border-radius: 10px; font-size: 0.85rem; font-weight: bold; }
        .add-to-cart {
            width: 100%;
            background: linear-gradient(135deg, #8B4513, #c49a6c);
            color: white;
            border: none;
            padding: 0.8rem;
            border-radius: 10px;
            font-weight: bold;
            cursor: pointer;
            transition: 0.3s;
        }
        .add-to-cart:hover { transform: translateY(-2px); }

        /* Footer */
        footer {
            background-color: #4b2e1e;
            color: white;
            text-align: center;
            padding: 20px 10px;
        }
    </style>
</head>
<body>
    <nav class="navbar">
        <div class="nav-container">
            <div class="logo">BrewMaster</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#menu">Menu</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <a href="#order" class="nav-cta">Order Now</a>
        </div>
    </nav>

    <section class="hero" id="home">
        <div class="hero-container">
            <div class="hero-content">
                <h1>BREW THE <span class="highlight">PERFECT</span> CUP</h1>
                <p>From bold espresso to creamy cappuccinos, BrewMaster brings you the finest coffee blends crafted to perfection.</p>
                <a href="#products" class="hero-cta">Shop Now</a>
            </div>
            <div class="hero-visual">
                <div class="main-product">
                    <img src="coffee-cup.png" alt="Premium Coffee Cup">
                </div>
            </div>
        </div>
    </section>

    <section class="products" id="products">
        <div class="products-container">
            <h2>Our Signature Blends</h2>
            <div class="products-flex-container">
                <div class="product-card">
                    <div class="product-image">
                        <img src="espresso.png" alt="Espresso Roast">
                    </div>
                    <div class="product-info">
                        <h3>Espresso Roast</h3>
                        <p>Rich and intense, with deep caramel sweetness and hints of dark chocolate.</p>
                        <div class="product-details">
                            <span class="price">$12.99</span>
                            <span class="caffeine">150mg</span>
                        </div>
                        <button class="add-to-cart">Add to Cart</button>
                    </div>
                </div>

                <div class="product-card">
                    <div class="product-image">
                        <img src="latte.png" alt="Vanilla Latte">
                    </div>
                    <div class="product-info">
                        <h3>Vanilla Latte</h3>
                        <p>Silky steamed milk with a smooth espresso base and a dash of vanilla.</p>
                        <div class="product-details">
                            <span class="price">$9.49</span>
                            <span class="caffeine">120mg</span>
                        </div>
                        <button class="add-to-cart">Add to Cart</button>
                    </div>
                </div>

                <div class="product-card">
                    <div class="product-image">
                        <img src="coldbrew.png" alt="Cold Brew">
                    </div>
                    <div class="product-info">
                        <h3>Cold Brew</h3>
                        <p>Brewed for 18 hours for a smooth, naturally sweet, and low-acid coffee.</p>
                        <div class="product-details">
                            <span class="price">$7.99</span>
                            <span class="caffeine">200mg</span>
                        </div>
                        <button class="add-to-cart">Add to Cart</button>
                    </div>
                </div>

                <div class="product-card">
                    <div class="product-image">
                        <img src="mocha.png" alt="Mocha Bliss">
                    </div>
                    <div class="product-info">
                        <h3>Mocha Bliss</h3>
                        <p>Chocolate and coffee come together in a decadent, creamy delight.</p>
                        <div class="product-details">
                            <span class="price">$10.79</span>
                            <span class="caffeine">140mg</span>
                        </div>
                        <button class="add-to-cart">Add to Cart</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <p>&copy; 2025 BrewMaster Coffee Co. All rights reserved.</p>
    </footer>
</body>
</html>
```

## OUTPUT
<img width="1875" height="845" alt="image" src="https://github.com/user-attachments/assets/f3e6eeee-7a6a-4b23-b982-6837ebeac183" />
<img width="1877" height="873" alt="image" src="https://github.com/user-attachments/assets/8eb6f619-6ceb-4626-a87d-784e77d8ff00" />
<img width="1855" height="881" alt="image" src="https://github.com/user-attachments/assets/cf55737c-93f6-4cf8-8a99-f76eb70c795e" />



## RESULT
The program for creating a commercial website using **CSS Flexbox** was executed successfully.
