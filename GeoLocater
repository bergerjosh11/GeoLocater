require 'geocoder'

# Replace this with your own GeoIP API key or use a different service if needed
Geocoder.configure(api_key: 'Put_API_key_here')

# Define a basic User class
class User
  include Geocoder::Model::Mongoid # Replace with your preferred ORM

  # Replace with your user model attributes
  attr_accessor :email, :ip_address

  geocoded_by :ip_address

  def initialize(email, ip_address)
    @email = email
    @ip_address = ip_address
  end

  def log_in
    if valid_login? # Replace with your authentication logic
      # Track IP address and get location
      geocode
      puts "Logged in successfully from IP: #{@ip_address}"
      puts "Approximate Location: #{location}"
    else
      puts 'Invalid credentials'
    end
  end

  private

  def valid_login?
    # Replace with your authentication logic (e.g., checking email and password)
    true # Replace this with your actual validation logic
  end
end

# Example usage:
user = User.new('user@example.com', '8.8.8.8') # Replace with actual user data
user.log_in
