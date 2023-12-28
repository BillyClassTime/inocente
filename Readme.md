## Static Web App

- Crear la aplicacion `static web app`

  ```powershell
  dotnet new blazorwasm
  ```

- Cambiar las páginas necesarias

  ```html
  <!--Counter.razor:-->
  @page "/counter"
  
  <PageTitle>Explanation</PageTitle>
  
  <h1>Explanation, read carefully </h1>
  
  <img src="/images/explanation.png" alt="Explanation" />
  ```

   

  ```html
  <!--  Home.razor -->
  @page "/"
  
  <PageTitle>Real Evidence</PageTitle>
  
  <h1>Evidence discovered</h1>
  
  <img src="/images/evidence.png" alt="evidence watermark ">
  ```

  

  ```html
  <!-- NavMenu.Razor -->
  <div class="top-row ps-3 navbar navbar-dark">
      <div class="container-fluid">
          <a class="navbar-brand" href="">Mady by ChatGPT</a>
          <button title="Navigation menu" class="navbar-toggler" @onclick="ToggleNavMenu">
              <span class="navbar-toggler-icon"></span>
          </button>
      </div>
  </div>
  
  <div class="@NavMenuCssClass nav-scrollable" @onclick="ToggleNavMenu">
      <nav class="flex-column">
          <div class="nav-item px-3">
              <NavLink class="nav-link" href="" Match="NavLinkMatch.All">
                  <span class="bi bi-house-door-fill-nav-menu" aria-hidden="true"></span> See real
              </NavLink>
          </div>
          <div class="nav-item px-3">
              <NavLink class="nav-link" href="counter">
                  <span class="bi bi-plus-square-fill-nav-menu" aria-hidden="true"></span> Explanations
              </NavLink>
          </div>
      </nav>
  </div>
  
  @code {
      private bool collapseNavMenu = true;
  
      private string? NavMenuCssClass => collapseNavMenu ? "collapse" : null;
  
      private void ToggleNavMenu()
      {
          collapseNavMenu = !collapseNavMenu;
      }
  }
  ```

- Probarla

  ```powershell
  dotnet run
  ```

- Publicarla

  ```powershell
  dotnet publish -c Release --output publish
  ```

- Crear el repositorio y subirlo a github

  