# Login-form-Design
{% extends "main.html" %}
{% block title %}
<title>Login</title>
{% endblock title %}
{%block body %}
{% with messages = get_flashed_messages(with_categories=true) %}
  {% if messages %}
    <ul class=flashes>
    {% for category, message in messages %}
    <div class="alert alert-{{category}} alert-dismissible fade show" role="alert">
        <strong>Message</strong> {{message}}
        <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
      </div>
    {% endfor %}
    </ul>
  {% endif %}
{% endwith %}
<h1 class='text-center'>Login page</h1>
<form method='POST' action='/login' class='my-5'>
  <div class="mb-3">
    <label for="exampleInputEmail1" class="form-label">Username</label>
    <input type="text" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" name='username'>
    
  </div>
  <div class="mb-3">
    <label for="exampleInputPassword1" class="form-label">Password</label>
    <input type="password" class="form-control" id="exampleInputPassword1" name='password'>
  </div>
  
  <button type="submit" class="btn btn-primary">Login</button>
</form>
{%endblock body%}
