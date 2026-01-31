# ITE501 Starter API (Node.js/Express) — Student/Employee Management     

This is a **ready-made REST API** for ITE501 projects. Students should:
1) Download this project, **push to their own GitHub repo**,  
2) Make minor changes (config, small endpoint change, etc.),  
3) Deploy on AWS (EC2 + ALB + ASG) and automate via CI/CD.

## Features
- CRUD for **Students** and **Employees**
- Simple **API-key authentication** via header `x-api-key`
- JSON file persistence (no database required)

## Quick Start (Local)
```bash
npm install
cp .env.example .env
npm start
```

API will run at: `http://localhost:3000`

## Authentication
Include header:
- `x-api-key: <your API key>`

Default key in `.env.example` is `changeme-ite501`.

## Endpoints
### Health
- `GET /health`

### Students
- `GET /api/students`
- `GET /api/students/:id`
- `POST /api/students`
- `PUT /api/students/:id`
- `DELETE /api/students/:id`

### Employees
- `GET /api/employees`
- `GET /api/employees/:id`
- `POST /api/employees`
- `PUT /api/employees/:id`
- `DELETE /api/employees/:id`

## Sample Requests
```bash
curl -H "x-api-key: changeme-ite501" http://localhost:3000/api/students
```

Create a student:
```bash
curl -X POST http://localhost:3000/api/students \
  -H "Content-Type: application/json" \
  -H "x-api-key: changeme-ite501" \
  -d '{"name":"Aisha","email":"aisha@adu.ac.ae","major":"Cloud Computing"}'
```

## Notes for AWS Deployment
- Use **systemd** or **pm2** (optional) to keep the API running on EC2.
- Configure **ALB target group health check** to `/health`.
- Keep `API_KEY` as an environment variable (do NOT hardcode).


## A summary of part A:

1. This project is a Node.js REST API developed for the ITE501 Cloud Computing final project.
2. The API manages Student and Employee data using a RESTful architecture.
3. API Key–based authentication is implemented to secure protected endpoints.
4. A public health check endpoint is included for application monitoring.
5. The application runs successfully in a local environment.
6. The project is version-controlled and hosted on a GitHub repository.
7. Environment variables are used for configuration and security.
8. The application is prepared for deployment on AWS EC2.
9. The design supports future integration with Load Balancer and Auto Scaling.
10. The project focuses on cloud deployment and DevOps practices rather than full application development....


## License
Educational use for ITE501.
