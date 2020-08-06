---
title: Autenticação no Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], authentication
- forms-based authentication [Reporting Services]
- authentication [Reporting Services]
- custom authentication [Reporting Services]
ms.assetid: 103ce1f9-31d8-44bb-b540-2752e4dcf60b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 59e97ba6ef849d8b4bfddfd6953c85826e351d6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574529"
---
# <a name="authentication-in-reporting-services"></a><span data-ttu-id="eddb6-102">Autenticação no Reporting Services</span><span class="sxs-lookup"><span data-stu-id="eddb6-102">Authentication in Reporting Services</span></span>
  <span data-ttu-id="eddb6-103">A autenticação é o processo de estabelecimento do direito de um usuário a uma identidade.</span><span class="sxs-lookup"><span data-stu-id="eddb6-103">Authentication is the process of establishing a user's right to an identity.</span></span> <span data-ttu-id="eddb6-104">Existem muitas técnicas que você pode usar para autenticar um usuário.</span><span class="sxs-lookup"><span data-stu-id="eddb6-104">There are many techniques that you can use to authenticate a user.</span></span> <span data-ttu-id="eddb6-105">O modo mais comum é usar senhas.</span><span class="sxs-lookup"><span data-stu-id="eddb6-105">The most common way is to use passwords.</span></span> <span data-ttu-id="eddb6-106">Quando você implementa a Autenticação de Formulários, por exemplo, deseja uma implementação que solicite credenciais dos usuários (normalmente por meio de alguma interface que solicita um nome de login e uma senha) e depois valide os usuários em um repositório de dados, como uma tabela de banco de dados ou um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="eddb6-106">When you implement Forms Authentication, for example, you want an implementation that queries users for credentials (usually by some interface that requests a login name and password) and then validates users against a data store, such as a database table or configuration file.</span></span> <span data-ttu-id="eddb6-107">Se as credenciais não puderem ser validadas, o processo de autenticação falhará e o usuário assumirá uma identidade anônima.</span><span class="sxs-lookup"><span data-stu-id="eddb6-107">If the credentials can't be validated, the authentication process fails and the user will assume an anonymous identity.</span></span>  
  
## <a name="custom-authentication-in-reporting-services"></a><span data-ttu-id="eddb6-108">Autenticação personalizada no Reporting Services</span><span class="sxs-lookup"><span data-stu-id="eddb6-108">Custom Authentication in Reporting Services</span></span>  
 <span data-ttu-id="eddb6-109">No [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], o sistema operacional Windows lida com a autenticação de usuários por meio da segurança integrada ou da recepção explícita e da validação de credenciais de usuário.</span><span class="sxs-lookup"><span data-stu-id="eddb6-109">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], the Windows operating system handles the authentication of users either through integrated security or through the explicit reception and validation of user credentials.</span></span> <span data-ttu-id="eddb6-110">A autenticação personalizada pode ser desenvolvida no [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] para dar suporte a esquemas de autenticação adicionais.</span><span class="sxs-lookup"><span data-stu-id="eddb6-110">Custom authentication can be developed in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] to support additional authentication schemes.</span></span> <span data-ttu-id="eddb6-111">Isso é possível por meio da interface de extensão de segurança <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>.</span><span class="sxs-lookup"><span data-stu-id="eddb6-111">This is made possible through the security extension interface <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>.</span></span> <span data-ttu-id="eddb6-112">Todas as extensões herdam da interface base <xref:Microsoft.ReportingServices.Interfaces.IExtension> para qualquer extensão implantada e usada pelo servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="eddb6-112">All extensions inherit from the <xref:Microsoft.ReportingServices.Interfaces.IExtension> base interface for any extension deployed and used by the report server.</span></span> <span data-ttu-id="eddb6-113"><xref:Microsoft.ReportingServices.Interfaces.IExtension>, além de <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>, são membros do namespace <xref:Microsoft.ReportingServices.Interfaces>.</span><span class="sxs-lookup"><span data-stu-id="eddb6-113"><xref:Microsoft.ReportingServices.Interfaces.IExtension>, as well as <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>, are members of the <xref:Microsoft.ReportingServices.Interfaces> namespace.</span></span>  
  
 <span data-ttu-id="eddb6-114">A principal forma de autenticar em um servidor de relatório no [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] é o método <xref:ReportService2010.ReportingService2010.LogonUser%2A>.</span><span class="sxs-lookup"><span data-stu-id="eddb6-114">The primary way to authenticate against a report server in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] is the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method.</span></span> <span data-ttu-id="eddb6-115">Esse membro do serviço Web Reporting Services pode ser usado para passar credenciais de usuário a um servidor de relatório para validação.</span><span class="sxs-lookup"><span data-stu-id="eddb6-115">This member of the Reporting Services Web service can be used to pass user credentials to a report server for validation.</span></span> <span data-ttu-id="eddb6-116">Sua extensão de segurança subjacente implementa **IAuthenticationExtension. LogonUser** que contém o código de autenticação personalizado.</span><span class="sxs-lookup"><span data-stu-id="eddb6-116">Your underlying security extension implements **IAuthenticationExtension.LogonUser** which contains your custom authentication code.</span></span> <span data-ttu-id="eddb6-117">Na amostra da Autenticação de Formulários, **LogonUser**, que executa uma verificação de autenticação nas credenciais fornecidas e em um repositório de usuários personalizado de um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="eddb6-117">In the Forms Authentication sample, **LogonUser**, which performs an authentication check against the supplied credentials and a custom user store in a database.</span></span> <span data-ttu-id="eddb6-118">Um exemplo de implementação de **LogonUser** é semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="eddb6-118">An example of an implementation of **LogonUser** looks like this:</span></span>  
  
```  
public bool LogonUser(string userName, string password, string authority)  
{  
   return AuthenticationUtilities.VerifyPassword(userName, password);  
}  
  
```  
  
 <span data-ttu-id="eddb6-119">A função de exemplo a seguir é usada para verificar as credenciais fornecidas:</span><span class="sxs-lookup"><span data-stu-id="eddb6-119">The following sample function is used to verify the supplied credentials:</span></span>  
  
```  
  
internal static bool VerifyPassword(string suppliedUserName,  
   string suppliedPassword)  
{   
   bool passwordMatch = false;  
   // Get the salt and pwd from the database based on the user name.  
   // See "How To: Use DPAPI (Machine Store) from ASP.NET," "How To:  
   // Use DPAPI (User Store) from Enterprise Services," and "How To:  
   // Create a DPAPI Library" for more information about how to use  
   // DPAPI to securely store connection strings.  
   SqlConnection conn = new SqlConnection(  
      "Server=localhost;" +   
      "Integrated Security=SSPI;" +  
      "database=UserAccounts");  
   SqlCommand cmd = new SqlCommand("LookupUser", conn);  
   cmd.CommandType = CommandType.StoredProcedure;  
  
   SqlParameter sqlParam = cmd.Parameters.Add("@userName",  
       SqlDbType.VarChar,  
       255);  
   sqlParam.Value = suppliedUserName;  
   try  
   {  
      conn.Open();  
      SqlDataReader reader = cmd.ExecuteReader();  
      reader.Read(); // Advance to the one and only row  
      // Return output parameters from returned data stream  
      string dbPasswordHash = reader.GetString(0);  
      string salt = reader.GetString(1);  
      reader.Close();  
      // Now take the salt and the password entered by the user  
      // and concatenate them together.  
      string passwordAndSalt = String.Concat(suppliedPassword, salt);  
      // Now hash them  
      string hashedPasswordAndSalt =  
         FormsAuthentication.HashPasswordForStoringInConfigFile(  
         passwordAndSalt,  
         "SHA1");  
      // Now verify them. Returns true if they are equal.  
      passwordMatch = hashedPasswordAndSalt.Equals(dbPasswordHash);  
   }  
   catch (Exception ex)  
   {  
       throw new Exception("Exception verifying password. " +  
          ex.Message);  
   }  
   finally  
   {  
       conn.Close();  
   }  
   return passwordMatch;  
}  
```  
  
## <a name="authentication-flow"></a><span data-ttu-id="eddb6-120">Fluxo de autenticação</span><span class="sxs-lookup"><span data-stu-id="eddb6-120">Authentication Flow</span></span>  
 <span data-ttu-id="eddb6-121">O serviço Web Reporting Services oferece extensões de autenticação personalizadas para habilitar a Autenticação de Formulários feita pelo Gerenciador de Relatórios e pelo servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="eddb6-121">The Reporting Services Web service provides custom authentication extensions to enable Forms Authentication by Report Manager and the report server.</span></span>  
  
 <span data-ttu-id="eddb6-122">O método <xref:ReportService2010.ReportingService2010.LogonUser%2A> do serviço Web Reporting Services é usado para enviar credenciais ao servidor de relatório para autenticação.</span><span class="sxs-lookup"><span data-stu-id="eddb6-122">The <xref:ReportService2010.ReportingService2010.LogonUser%2A> method of the Reporting Services Web service is used to submit credentials to the report server for authentication.</span></span> <span data-ttu-id="eddb6-123">O serviço Web usa cabeçalhos HTTP para passar um tíquete de autenticação (conhecido como "cookie") do servidor para o cliente para solicitações de logon validadas.</span><span class="sxs-lookup"><span data-stu-id="eddb6-123">The Web service uses HTTP headers to pass an authentication ticket (known as a "cookie") from the server to the client for validated logon requests.</span></span>  
  
 <span data-ttu-id="eddb6-124">A ilustração a seguir mostra o método de autenticação de usuários no serviço Web quando o seu aplicativo é implantado com um servidor de relatório configurado para usar uma extensão de autenticação personalizada.</span><span class="sxs-lookup"><span data-stu-id="eddb6-124">The following illustration depicts the method of authenticating users to the Web service when your application is deployed with a report server configured to use a custom authentication extension.</span></span>  
  
 <span data-ttu-id="eddb6-125">![Fluxo de autenticação de segurança do Reporting Services](../../media/rosettasecurityextensionauthenticationflow.gif "Fluxo de autenticação de segurança do Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="eddb6-125">![Reporting Services security authentication flow](../../media/rosettasecurityextensionauthenticationflow.gif "Reporting Services security authentication flow")</span></span>  
  
 <span data-ttu-id="eddb6-126">Como mostrado na Figura 2, o processo de autenticação é assim:</span><span class="sxs-lookup"><span data-stu-id="eddb6-126">As shown in Figure 2, the authentication process is as follows:</span></span>  
  
1.  <span data-ttu-id="eddb6-127">Um aplicativo cliente chama o método do serviço Web <xref:ReportService2010.ReportingService2010.LogonUser%2A> para autenticar um usuário.</span><span class="sxs-lookup"><span data-stu-id="eddb6-127">A client application calls the Web service <xref:ReportService2010.ReportingService2010.LogonUser%2A> method to authenticate a user.</span></span>  
  
2.  <span data-ttu-id="eddb6-128">O serviço Web faz uma chamada para o <xref:ReportService2010.ReportingService2010.LogonUser%2A> método de sua extensão de segurança, especificamente, a classe que implementa **IAuthenticationExtension**.</span><span class="sxs-lookup"><span data-stu-id="eddb6-128">The Web service makes a call to the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method of your security extension, specifically, the class that implements **IAuthenticationExtension**.</span></span>  
  
3.  <span data-ttu-id="eddb6-129">A sua implementação de <xref:ReportService2010.ReportingService2010.LogonUser%2A> valida o nome de usuário e a senha no repositório de usuários ou na autoridade de segurança.</span><span class="sxs-lookup"><span data-stu-id="eddb6-129">Your implementation of <xref:ReportService2010.ReportingService2010.LogonUser%2A> validates the user name and password in the user store or security authority.</span></span>  
  
4.  <span data-ttu-id="eddb6-130">Após a autenticação bem-sucedida, o serviço Web criará um cookie e o gerenciará para a sessão.</span><span class="sxs-lookup"><span data-stu-id="eddb6-130">Upon successful authentication, the Web service creates a cookie and manages it for the session.</span></span>  
  
5.  <span data-ttu-id="eddb6-131">O serviço Web devolve o tíquete de autenticação ao aplicativo de chamada no cabeçalho HTTP.</span><span class="sxs-lookup"><span data-stu-id="eddb6-131">The Web service returns the authentication ticket to the calling application on the HTTP header.</span></span>  
  
 <span data-ttu-id="eddb6-132">Quando o serviço Web autenticar um usuário com êxito por meio da extensão de segurança, vai gerar um cookie que será usado para as solicitações subsequentes.</span><span class="sxs-lookup"><span data-stu-id="eddb6-132">When the Web service successfully authenticates a user through the security extension, it generates a cookie that is used for subsequent requests.</span></span> <span data-ttu-id="eddb6-133">O cookie pode não persistir dentro da autoridade de segurança personalizada porque o servidor de relatório não possui a autoridade de segurança.</span><span class="sxs-lookup"><span data-stu-id="eddb6-133">The cookie may not persist within the custom security authority because the report server does not own the security authority.</span></span> <span data-ttu-id="eddb6-134">O cookie é retornado a partir do método <xref:ReportService2010.ReportingService2010.LogonUser%2A> do serviço Web e é usado em chamadas subsequentes do método do serviço Web e no acesso à URL.</span><span class="sxs-lookup"><span data-stu-id="eddb6-134">The cookie is returned from the <xref:ReportService2010.ReportingService2010.LogonUser%2A> Web service method and is used in subsequent Web service method calls and in URL access.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eddb6-135">Para impedir o comprometimento do cookie durante a transmissão, os cookies de autenticação retornados de <xref:ReportService2010.ReportingService2010.LogonUser%2A> devem ser transmitidos de forma segura usando criptografia SSL.</span><span class="sxs-lookup"><span data-stu-id="eddb6-135">In order to avoid compromising the cookie during transmission, authentication cookies returned from <xref:ReportService2010.ReportingService2010.LogonUser%2A> should be transmitted securely using Secure Sockets Layer (SSL) encryption.</span></span>  
  
 <span data-ttu-id="eddb6-136">Se você acessar o servidor de relatório por meio do acesso à URL quando uma extensão de segurança personalizada for instalada, o IIS (Serviços de Informações da Internet) e o [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] gerenciarão automaticamente a transmissão do tíquete de autenticação.</span><span class="sxs-lookup"><span data-stu-id="eddb6-136">If you access the report server through URL access when a custom security extension is installed, Internet Information Services (IIS) and [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] automatically manage the transmission of the authentication ticket.</span></span> <span data-ttu-id="eddb6-137">Se você estiver acessando o servidor de relatório por meio da API SOAP, a sua implementação da classe proxy deverá incluir suporte adicional para o gerenciamento do tíquete de autenticação.</span><span class="sxs-lookup"><span data-stu-id="eddb6-137">If you are accessing the report server through the SOAP API, your implementation of the proxy class must include additional support for managing the authentication ticket.</span></span> <span data-ttu-id="eddb6-138">Para obter mais informações sobre como usar a API SOAP e gerenciar o tíquete de autenticação, consulte "Usando o serviço Web com segurança personalizada".</span><span class="sxs-lookup"><span data-stu-id="eddb6-138">For more information about using the SOAP API and managing the authentication ticket, see "Using the Web Service with Custom Security."</span></span>  
  
## <a name="forms-authentication"></a><span data-ttu-id="eddb6-139">Autenticação de Formulários</span><span class="sxs-lookup"><span data-stu-id="eddb6-139">Forms Authentication</span></span>  
 <span data-ttu-id="eddb6-140">A Autenticação de Formulários é um tipo de autenticação do [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] na qual um usuário não autenticado é direcionado a um formulário HTML.</span><span class="sxs-lookup"><span data-stu-id="eddb6-140">Forms Authentication is a type of [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication in which an unauthenticated user is directed to an HTML form.</span></span> <span data-ttu-id="eddb6-141">Quando o usuário fornece credenciais, o sistema emite um cookie com um tíquete de autenticação.</span><span class="sxs-lookup"><span data-stu-id="eddb6-141">Once the user provides credentials, the system issues a cookie containing an authentication ticket.</span></span> <span data-ttu-id="eddb6-142">Em solicitações posteriores, o sistema verifica o cookie primeiro para ver se o usuário já foi autenticado pelo servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="eddb6-142">On later requests, the system first checks the cookie to see if the user was already authenticated by the report server.</span></span>  
  
 <span data-ttu-id="eddb6-143">O [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] pode ser estendido para dar suporte à Autenticação de Formulários que usa as interfaces de extensibilidade de segurança disponíveis por meio da API do Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="eddb6-143">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] can be extended to support Forms Authentication using the security extensibility interfaces available through the Reporting Services API.</span></span> <span data-ttu-id="eddb6-144">Se você estender o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] para usar a Autenticação de Formulários, use o protocolo SSL (Secure Sockets Layer) para todas as comunicações feitas com o servidor de relatório para impedir que usuários maliciosos obtenham acesso ao cookie de outro usuário.</span><span class="sxs-lookup"><span data-stu-id="eddb6-144">If you extend [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] to use Forms Authentication, use Secure Sockets Layer (SSL) for all communications with the report server to prevent malicious users from gaining access to another user's cookie.</span></span> <span data-ttu-id="eddb6-145">O SSL permite que clientes e que um servidor de relatório autentiquem uns aos outros e garantam que nenhum outro computador poderá ler o conteúdo das comunicações entre os dois computadores.</span><span class="sxs-lookup"><span data-stu-id="eddb6-145">SSL enables clients and a report server to authenticate each other and to ensure that no other computers can read the contents of communications between the two computers.</span></span> <span data-ttu-id="eddb6-146">Todos os dados enviados de um cliente por meio de uma conexão SSL são criptografados para que os usuários maliciosos não possam interceptar senhas ou dados enviados para um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="eddb6-146">All data sent from a client through an SSL connection is encrypted so that malicious users cannot intercept passwords or data sent to a report server.</span></span>  
  
 <span data-ttu-id="eddb6-147">A Autenticação de Formulário é geralmente implementada para dar suporte a contas e à autenticação para plataformas diferentes do Windows.</span><span class="sxs-lookup"><span data-stu-id="eddb6-147">Forms Authentication is generally implemented to support accounts and authentication for platforms other than Windows.</span></span> <span data-ttu-id="eddb6-148">Uma interface gráfica é apresentada a um usuário que solicite acesso a um servidor de relatório e as credenciais fornecidas serão enviadas a uma autoridade de segurança para autenticação.</span><span class="sxs-lookup"><span data-stu-id="eddb6-148">A graphical interface is presented to a user who requests access to a report server, and the supplied credentials are submitted to a security authority for authentication.</span></span>  
  
 <span data-ttu-id="eddb6-149">A Autenticação de Formulários exige que uma pessoa esteja presente para inserir as credenciais.</span><span class="sxs-lookup"><span data-stu-id="eddb6-149">Forms Authentication requires that a person is present to enter credentials.</span></span> <span data-ttu-id="eddb6-150">Para aplicativos autônomos que se comunicam diretamente com o serviço Web Reporting Services, a Autenticação de Formulários deve ser combinada a um esquema de autenticação personalizado.</span><span class="sxs-lookup"><span data-stu-id="eddb6-150">For unattended applications that communicate directly with the Reporting Services Web service, Forms Authentication must be combined with a custom authentication scheme.</span></span>  
  
 <span data-ttu-id="eddb6-151">A Autenticação de Formulários é apropriada para o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] quando:</span><span class="sxs-lookup"><span data-stu-id="eddb6-151">Forms Authentication is appropriate for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] when:</span></span>  
  
-   <span data-ttu-id="eddb6-152">Você precisa armazenar e autenticar usuários que não têm contas do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] o Windows e</span><span class="sxs-lookup"><span data-stu-id="eddb6-152">You need to store and authenticate users that do not have [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows accounts, and</span></span>  
  
-   <span data-ttu-id="eddb6-153">Você precisa fornecer o seu próprio formulário de interface do usuário como página de logon entre páginas diferentes de um site.</span><span class="sxs-lookup"><span data-stu-id="eddb6-153">You need to provide your own user interface form as a logon page between different pages on a Web site.</span></span>  
  
 <span data-ttu-id="eddb6-154">Considere o seguinte ao escrever uma extensão de segurança personalizada que dê suporte à Autenticação de Formulários:</span><span class="sxs-lookup"><span data-stu-id="eddb6-154">Consider the following when writing a custom security extension that supports Forms Authentication:</span></span>  
  
-   <span data-ttu-id="eddb6-155">Se você usar a Autenticação de Formulários, o acesso anônimo deverá ser habilitado no diretório virtual de servidor de relatório no IIS (Serviços de Informações da Internet).</span><span class="sxs-lookup"><span data-stu-id="eddb6-155">If you use Forms Authentication, anonymous access must be enabled on the report server virtual directory in Internet Information Services (IIS).</span></span>  
  
-   <span data-ttu-id="eddb6-156">A autenticação do [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] deve ser definida como Formulários.</span><span class="sxs-lookup"><span data-stu-id="eddb6-156">[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication must be set to Forms.</span></span> <span data-ttu-id="eddb6-157">Você configura autenticação do [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] no arquivo Web.config para o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="eddb6-157">You configure [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication in the Web.config file for the report server.</span></span>  
  
-   <span data-ttu-id="eddb6-158">O [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] pode autenticar e autorizar usuários com a Autenticação do Windows ou a autenticação personalizada, mas não com ambas.</span><span class="sxs-lookup"><span data-stu-id="eddb6-158">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] can authenticate and authorize users with either Windows Authentication or custom authentication, but not both.</span></span> <span data-ttu-id="eddb6-159">O [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] não dá suporte ao uso simultâneo de várias extensões de segurança.</span><span class="sxs-lookup"><span data-stu-id="eddb6-159">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] does not support simultaneous use of multiple security extensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eddb6-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eddb6-160">See Also</span></span>  
 [<span data-ttu-id="eddb6-161">Implementando uma extensão de segurança</span><span class="sxs-lookup"><span data-stu-id="eddb6-161">Implementing a Security Extension</span></span>](../security-extension/implementing-a-security-extension.md)  
  
  
