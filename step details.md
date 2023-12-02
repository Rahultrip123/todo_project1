how to use and test your APIs using Django Rest Framework (DRF) Browsable API:

Step 1: Install Django Rest Framework
=====================================
Ensure that Django Rest Framework is installed. You can install it using:


pip install djangorestframework


Step 2: Configure Django Rest Framework
=====================================
In your settings.py file, add 'rest_framework' to the INSTALLED_APPS:


# settings.py
INSTALLED_APPS = [
    # ...
    'rest_framework',
    'api',  # Assuming 'api' is the name of your Django app
    # ...
]
Step 3: Add Browsable API URLs
=====================================
Update your api/urls.py file to include the DRF Browsable API views:


# api/urls.py

from django.urls import path, include
from api.views import CompanyViewSet, EmployeeViewSet
from rest_framework import routers

router = routers.DefaultRouter()
router.register(r'companies', CompanyViewSet)
router.register(r'employees', EmployeeViewSet)

urlpatterns = [
    path('', include(router.urls)),
    path('api-auth/', include('rest_framework.urls', namespace='rest_framework')),
]
Step 4: Run Django Development Server
=====================================
Start your Django development server:

python manage.py runserver


Step 5: Access Browsable API
=====================================
Visit the following URL in your browser to access the DRF Browsable API login page:

http://localhost:8000/api/v1/api-auth/

Step 6: Log in
=====================================
Log in using your Django admin credentials.

Step 7: Explore Companies API
=====================================
Navigate to the Companies API view:


http://localhost:8000/api/v1/companies/
Here, you can view existing companies, create new ones, and perform other CRUD operations.

Step 8: Explore Employees API
=====================================
Navigate to the Employees API view:


http://localhost:8000/api/v1/employees/
Similar to the Companies API, you can interact with the Employees API, view records, and perform CRUD operations.

Step 9: Test Custom Endpoint
=====================================
Explore the custom endpoint for retrieving employees of a specific company:


http://localhost:8000/api/v1/companies/{companyId}/employees/
Replace {companyId} with the actual ID of a company.

Step 10: Review API Documentation
=====================================
As you explore the Browsable API, take note of the documentation provided for each endpoint. DRF automatically generates documentation based on your serializers and views.

step 11:you can also check the sqliteviewer.app
================================================
https://sqliteviewer.app/

You've successfully set up and tested your APIs using Django Rest Framework's Browsable API. This provides a convenient way to interact with and understand your API functionality.





