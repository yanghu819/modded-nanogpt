The code snippet implements Gram-Schmidt orthogonalization to ensure the gradient is orthogonal to the momentum direction:
```python
    ref_norm = ref / (ref.norm() + eps)  # Normalize the momentum vector
    proj = g @ ref_norm.T @ ref_norm     # Project gradient onto momentum direction
    g_orth = g - proj                    # Remove the projected component
```

This process:

First normalizes the momentum vector for numerical stability
Then computes the projection of the gradient onto the momentum direction
Finally subtracts this projection to obtain the orthogonal component
The resulting g_orth is guaranteed to be orthogonal to the momentum direction
