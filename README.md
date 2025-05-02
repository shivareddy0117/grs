# GRS Systems Website

A professional IT consulting company website built with HTML, CSS, and JavaScript.

## Features

- Modern, responsive design
- Smooth scrolling navigation
- Contact form
- Service showcase
- Mobile-friendly layout

## Deployment Instructions

### Prerequisites

- Azure account
- Azure CLI installed
- Git installed

### Steps to Deploy to Azure

1. **Create an Azure Web App**
   ```bash
   az webapp create --resource-group <your-resource-group> --plan <your-app-service-plan> --name <your-webapp-name>
   ```

2. **Configure Deployment Credentials**
   ```bash
   az webapp deployment user set --user-name <username> --password <password>
   ```

3. **Configure Local Git Deployment**
   ```bash
   az webapp deployment source config-local-git --name <your-webapp-name> --resource-group <your-resource-group>
   ```

4. **Get the Git URL**
   ```bash
   az webapp deployment source config-local-git --name <your-webapp-name> --resource-group <your-resource-group> --query url --output tsv
   ```

5. **Deploy the Website**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add azure <git-url-from-step-4>
   git push azure master
   ```

### Alternative Deployment Method (Using Azure Static Web Apps)

1. **Create a GitHub repository** and push your code to it.

2. **Create an Azure Static Web App**
   - Go to Azure Portal
   - Click "Create a resource"
   - Search for "Static Web Apps"
   - Fill in the required details
   - Connect to your GitHub repository
   - Configure build settings:
     - App location: `/`
     - Api location: (leave empty)
     - App artifact location: `/`

3. **Review and create** the Static Web App

## Local Development

1. Clone the repository
2. Open `index.html` in your browser
3. Make changes to the files as needed

## File Structure

```
src/
├── components/
│   └── main.js
├── styles/
│   └── main.css
├── pages/
│   └── index.html
└── public/
    └── images/
```

## Customization

- Update the content in `index.html` to match your company's information
- Modify colors and styles in `main.css`
- Add your own images to the `public/images` directory
- Update the contact form handling in `main.js` to connect to your backend service

## Support

For any questions or issues, please contact the development team. 