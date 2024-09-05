# faq-of-ds-at-tripleten

# General Questions

## Useful links

### Free resource for practicing Python

[Python Exercises](https://pynative.com/python-exercises-with-solutions/)

[W3Schools](https://www.w3schools.com/python/default.asp)

## About the dataframe variables in Jupyter Notebooks

```mermaid
graph TD
    A[df] --> |Remove missing values| B[df]
    B[df] --> |Remove duplicates| C[df]
    C[df] --> |Rename / convert datatype | D[cleaned_df]
    D[cleaned_df] --> |Apply filters| E[filtered_df]
    K[other_df] --> |join/merge| F[engineered_df]
    D[cleaned_df] --> | Feature Engineering| F[engineered_df]
    E[filtered_df] --> |Perform analysis| G[analyzed_df]
    F[engineered_df] --> |Build and validate model| H[modeling_df]
    classDef milestone fill:#f9f,stroke:#333,stroke-width:2px;

    D:::milestone
    E:::milestone
    F:::milestone


```
