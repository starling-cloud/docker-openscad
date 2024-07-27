# syntax=docker/dockerfile:1.4

# Base Image
# =============================================================================
# Use an explicit version of Ubuntu to ensure consistency across builds
FROM ubuntu:22.04 as base

# Install OpenSCAD
RUN apt-get update && \
    apt-get install -y openscad && \
    rm -rf /var/lib/apt/lists/*  # Clean up to reduce image size

# Set the working directory
WORKDIR /usr/src/app

# Copy the local OpenSCAD files into the container
COPY . .

# Final Image
# =============================================================================
FROM base as final

# Set the entry point to OpenSCAD CLI
ENTRYPOINT ["openscad"]
# Default command shows help, override to open specific files or run scripts
CMD ["--help"]