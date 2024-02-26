---
type: Topic note
tags: 
created: 2024-02-26 18:52
---
Temporary transfer of [[Ownership|ownership]] in [[Rust]].

- The two types of borrows have roots in the [[Rust#Shared `xor` mutable|shared xor mutable]] principle of [[Rust]].

# Syntax

The ampersand (`&`) is used to denote [[Borrowing]]. `&` denotes shared borrows, `&mut` denotes exclusive borrows.

# Shared borrows

Multiple shared borrows can be distributed at the same time. However, shared borrows are immutable, read only.

# Exclusive borrows

Only one borrow can be distributed at any point in time, but the value can be mutated. It is also not possible to have an exclusive borrow and a shared borrow simultaneously.

Note that this means **the value itself must be declared as mutable.**

# Which borrow to use?

The [Rust documentation](https://docs.rs) will tell you whether a library function necessitates the use of exclusive borrows.

Otherwise, begin with shared borrows. If mutation is necessary, change it to exclusive borrow.

# Example

```rust
pub fn main() {
	let mut image = Image::new(256, 256);
	
	// The borrow will expire after this line
	draw_line(&mut image, 20, 20, 80, LineDirection::Horizontal);
	
	image.save("my_image.bmp").unwrap();
}

fn draw_line(image: &mut Image, x: u32, y: u32, length: u32, direction: LineDirection) -> Image {
	for i in 0..length {
		let (cur_x, cur_y) = match direction {
			LineDirection::Horizontal => {
				(x + i, y)
			}
			
			LineDirection::Vertical => {
				(x, y + i)
			}
		};
		
		image.set_pixel(cur_x, cur_y, bmp::consts::RED);
	}
	
	image 
}
```

Here, a mutable reference, or an exclusive borrow, is required by `ìmage.set_pixel`.

---
# References
