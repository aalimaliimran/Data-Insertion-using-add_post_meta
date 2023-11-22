# Data-Insertion-using-add_post_meta

```markdown
# WordPress Database Connection and Data Insertion

## Prerequisites

- WordPress installed on your server.
- Basic knowledge of WordPress development.

## Database Connection

To connect to the WordPress database, you can use the built-in `$wpdb` class. In your PHP file, add the following lines:

```php
// Include WordPress core files
require_once('path/to/your/wp-config.php');

// Create a global $wpdb object
global $wpdb;
```

Replace `'path/to/your/wp-config.php'` with the correct path to your `wp-config.php` file.

## Data Insertion using add_post_meta

Once connected to the database, you can use the `add_post_meta` function to insert data into the WordPress database. Here's an example:

```php
// Example data to insert
$my_post = array(
    'post_title'    => 'My Post Title',
    'post_content'  => 'This is the content of my post.',
    'post_status'   => 'publish',
    'post_author'   => 1, // Change this to the desired author's ID
    'post_type'     => 'post', // Change this to the desired post type
);

// Insert the post and get the post ID
$post_id = wp_insert_post($my_post);

// Check if the post was successfully inserted
if (!is_wp_error($post_id)) {
    // Insert additional data using add_post_meta
    add_post_meta($post_id, 'ai_car_name', $_SESSION['booking_data']['car_name'], true);

    echo 'Post created successfully with ID: ' . $post_id;
} else {
    echo 'Error creating post: ' . $post_id->get_error_message();
}
```

Replace the values in `$my_post` with your desired post details. The `add_post_meta` function is then used to add custom meta data to the created post. Adjust the meta key and value accordingly.

Feel free to explore more WordPress functions and customize the code based on your specific use case.
```

This README provides a basic guide for users to understand how to connect to the WordPress database and insert data using the `add_post_meta` function. Adjust the paths, post details, and other parameters as needed for your specific WordPress setup.
