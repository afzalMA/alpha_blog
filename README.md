<div class="container">
  <% if @article.errors.any? %>
    <h2>The following errors prevented the article from being saved</h2>
    <ul>
      <% @article.errors.full_messages.each do |msg| %>
        <li><%= msg %></li>
      <% end %>
    </ul>
  <% end %>
  <div class="row justify-content-center">
    <div class="col-10">
      <%= form_with(model: @article, class: "shadow p-3 mb-3 bg-info rounded", local: true) do |f| %>
        <div class="form-group row">
          <%= f.label :title, class: "col-2 col-form-label text-light" %>
          <div class="col-10">
            <%= f.text_field :title, class: "form-control shadow rounded", placeholder: "Title of article" %>
          </div>
        </div>
        <div class="form-group row">
          <%= f.label :description, class: "col-2 col-form-label text-light" %>
          <div class="col-10"> 
            <%= f.text_area :description, rows: 10, class: "form-control shadow rounded", placeholder: "Description of article" %>
          </div>
        </div>
        <div class="form-group row justify-content-center">
          <%= f.submit class: "btn btn-outline-light btn-lg" %>
        </div>
      <% end %>
    </div>
    <%= link_to '[ Cancel and return to articles listing ]', articles_path, class: "text-info" %>
  </div>
</div> 