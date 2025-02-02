[Back to Main README](../README.md)

## System Concepts 

### Overview

                         +-------------------------------------+
                         |      Local Client Application       |
                         |                                     |
                         |  +-----------------------------+    |
                         |  |    PyQt GUI (Data Entry)    |    |
                         |  +-------------+---------------+    |
                         |                |                    |
                         |                v                    |
                         |  +-----------------------------+    |
                         |  |   Data Anonymization Module |    |
                         |  +-------------+---------------+    |
                         |                |                    |
                         |                v                    |
                         |  +-----------------------------+    |
                         |  | Local SQLite Database       |    |
                         |  | (with SQLCipher encryption) |    |
                         |  +-------------+---------------+    |
                         |                |                    |
                         |                v                    |
                         |  +-----------------------------+    |
                         |  | JSON Serialization Module   |    |
                         |  +-------------+---------------+    |
                         |                |                    |
                         |                v                    |
                         |  +-----------------------------+    |
                         |  | Secure Transmission (HTTPS) |    |
                         |  |   via requests library      |    |
                         |  +-------------+---------------+    |
                         +---------------------|---------------+
                                               |
                                               v
                                   [ Internet / Secure Channel ]
                                               |
                                               v
                         +-------------------------------------+
                         |         Cloud Backend (Django)      |
                         |                                     |
                         |  +-----------------------------+    |
                         |  | Django REST API             |    |
                         |  | (Django + DRF*)             |    |
                         |  +-------------+---------------+    |
                         |                |                    |
                         |                v                    |
                         |  +-----------------------------+    |
                         |  | PostgreSQL Database         |    |
                         |  +-------------+---------------+    |
                         |                |                    |
                         |                v                    |
                         |  +-----------------------------+    |
                         |  | Celery Task Queue           |    |
                         |  | (with Redis/RabbitMQ)       |    |
                         |  +-------------+---------------+    |
                         |                |                    |
                         |                v                    |
                         |  +-----------------------------+    |
                         |  | AI Analysis Module          |    |
                         |  | (scikit-learn /             |    |
                         |  |  TensorFlow / PyTorch)      |    |
                         |  +-------------+---------------+    |
                         |                |                    |
                         |                v                    |
                         |  +-----------------------------+    |
                         |  | Vector Database             |    |
                         |  | (Milvus / Qdrant / Weaviate)|    |
                         |  +-------------+---------------+    |
                         |                |                    |
                         |                v                    |
                         |  +-----------------------------+    |
                         |  | Django Admin Interface      |    |
                         |  +-----------------------------+    |
                         +-------------------------------------+



<details>
  <summary>Detailed system concepts and techstack</summary>
  
  <h4>System Concepts</h4>
  <ul>
    <li>
      <strong>Local Client Application:</strong>  
      A desktop application (built with Python and PyQt) for data entry,
      local storage (using SQLite with SQLCipher for encryption), and
      initial data anonymization.
    </li>
    <li>
      <strong>Cloud Backend:</strong>  
      A Django-based API (leveraging Django REST Framework) that securely
      receives anonymized data from the local client and stores it in
      a robust database (PostgreSQL).
    </li>
    <li>
      <strong>Asynchronous Processing:</strong>  
      A Celery Task Queue (using Redis or RabbitMQ) that schedules and
      manages background tasks—most notably, triggering AI analysis.
    </li>
    <li>
      <strong>AI Analysis Module:</strong>  
      A dedicated module that processes data using machine learning
      libraries (scikit-learn, TensorFlow, or PyTorch) to generate insights
      and vector representations.
    </li>
    <li>
      <strong>Vector Database:</strong>  
      A specialized database (e.g., Milvus, Qdrant, or Weaviate) to store
      high-dimensional vectors, enabling efficient similarity searches and
      advanced analytics.
    </li>
    <li>
      <strong>Django Admin Interface:</strong>  
      A built-in, customizable administrative dashboard for system monitoring,
      data management, and operational control.
    </li>
  </ul>

  <h4>Technology Stack</h4>
  <ul>
    <li>
      <strong>Frontend (Local):</strong>  
      Python, PyQt, SQLite (with SQLCipher)
    </li>
    <li>
      <strong>Backend:</strong>  
      Python, Django, Django REST Framework, SQLite (PostgreSQL for production)
    </li>
    <li>
      <strong>Asynchronous Processing:</strong>  
      Celery, Redis/RabbitMQ
    </li>
    <li>
      <strong>AI &amp; Machine Learning:</strong>  
      scikit-learn, TensorFlow, PyTorch
    </li>
    <li>
      <strong>Vector Database:</strong>  
      Milvus / Qdrant / Weaviate
    </li>
  </ul>
</details>


[Back to Main README](../README.md)
