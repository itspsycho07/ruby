FROM ruby:3.0-alpine

# Install dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    nodejs \
    postgresql-client

# Set the working directory
WORKDIR /app

# Install bundler
RUN gem install bundler

# Copy the Gemfile and Gemfile.lock
COPY Gemfile Gemfile.lock ./

# Install gems
RUN bundle install

# Copy the application code
COPY . .

# Start the Rails server
CMD ["rails", "server", "-b", "0.0.0.0"]
