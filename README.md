from zeep import Client

# Define the SOAP endpoint URL
url = 'http://www.dneonline.com/calculator.asmx?WSDL'

# Create a SOAP client
client = Client(url)

# Call a SOAP method to get the available operations
available_operations = client.wsdl.services[0].ports[0].methods.keys()

# Print the available operations
print("Available SOAP operations:")
for operation in available_operations:
    print(operation)

# Call a specific SOAP method
result = client.service.Add(5, 10)

# Print the result
print("Result of adding 5 and 10:", result)
