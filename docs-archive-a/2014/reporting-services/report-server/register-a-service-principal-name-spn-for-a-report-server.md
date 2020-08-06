---
title: Registrar um SPN (Nome da Entidade de Serviço) para um servidor de relatório | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dda91d4f-77cc-4898-ad03-810ece5f8e74
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 502170f16aad66757e8f44419ccbac3017072449
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583378"
---
# <a name="register-a-service-principal-name-spn-for-a-report-server"></a><span data-ttu-id="2493a-102">Registrar um SPN (Nome da Entidade de Serviço) para um servidor de relatório</span><span class="sxs-lookup"><span data-stu-id="2493a-102">Register a Service Principal Name (SPN) for a Report Server</span></span>
  <span data-ttu-id="2493a-103">Se estiver implantando o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] em uma rede que use o protocolo Kerberos para autenticação mútua, você deverá criar um SPN (Nome da Entidade de Serviço) para o serviço Servidor de Relatório se configurá-lo para execução como uma conta de usuário do domínio.</span><span class="sxs-lookup"><span data-stu-id="2493a-103">If you are deploying [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in a network that uses the Kerberos protocol for mutual authentication, you must create a Service Principal Name (SPN) for the Report Server service if you configure it to run as a domain user account.</span></span>  
  
## <a name="about-spns"></a><span data-ttu-id="2493a-104">Sobre SPNs</span><span class="sxs-lookup"><span data-stu-id="2493a-104">About SPNs</span></span>  
 <span data-ttu-id="2493a-105">Um SPN é um identificador exclusivo para um serviço em uma rede que usa autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="2493a-105">An SPN is a unique identifier for a service on a network that uses Kerberos authentication.</span></span> <span data-ttu-id="2493a-106">Consiste em uma classe de serviço, um nome de host e uma porta.</span><span class="sxs-lookup"><span data-stu-id="2493a-106">It consists of a service class, a host name, and a port.</span></span> <span data-ttu-id="2493a-107">Em uma rede que usa autenticação Kerberos, deve ser registrado um SPN para o servidor em uma conta interna do computador (como NetworkService ou LocalSystem) ou uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="2493a-107">On a network that uses Kerberos authentication, an SPN for the server must be registered under either a built-in computer account (such as NetworkService or LocalSystem) or user account.</span></span> <span data-ttu-id="2493a-108">Os SPNs são automaticamente registrados para contas internas.</span><span class="sxs-lookup"><span data-stu-id="2493a-108">SPNs are registered for built-in accounts automatically.</span></span> <span data-ttu-id="2493a-109">Entretanto, quando executar um serviço em uma conta de usuário do domínio, você deverá registrar manualmente o SPN para a conta que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="2493a-109">However, when you run a service under a domain user account, you must manually register the SPN for the account you want to use.</span></span>  
  
 <span data-ttu-id="2493a-110">Para criar um SPN, você pode usar o utilitário de linha de comando **SetSPN** .</span><span class="sxs-lookup"><span data-stu-id="2493a-110">To create an SPN, you can use the **SetSPN** command line utility.</span></span> <span data-ttu-id="2493a-111">Para saber mais, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2493a-111">For more information, see the following:</span></span>  
  
-   <span data-ttu-id="2493a-112">[Setspn](https://technet.microsoft.com/library/cc731241\(WS.10\).aspx) ( https://technet.microsoft.com/library/cc731241(WS.10).aspx) .</span><span class="sxs-lookup"><span data-stu-id="2493a-112">[Setspn](https://technet.microsoft.com/library/cc731241\(WS.10\).aspx) (https://technet.microsoft.com/library/cc731241(WS.10).aspx).</span></span>  
  
-   <span data-ttu-id="2493a-113">[Nome da entidade de serviço (SPNs) sintaxe SetSPN (Setspn.exe)](https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) ( https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) .</span><span class="sxs-lookup"><span data-stu-id="2493a-113">[Service Principal Names (SPNs) SetSPN Syntax (Setspn.exe)](https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) (https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx).</span></span>  
  
 <span data-ttu-id="2493a-114">Você deve ser um administrador de domínio para executar o utilitário no controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="2493a-114">You must be a domain administrator to run the utility on the domain controller.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2493a-115">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2493a-115">Syntax</span></span>  
 <span data-ttu-id="2493a-116">A sintaxe de comando para usar o utilitário SetSPN e criar um SPN para o servidor de relatório se assemelha ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="2493a-116">The command syntax for using SetSPN utility to create an SPN for the report server resembles the following:</span></span>  
  
```  
Setspn -s http/<computername>.<domainname>:<port> <domain-user-account>  
```  
  
 <span data-ttu-id="2493a-117">**SetSPN** está disponível no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="2493a-117">**SetSPN** is available with Windows Server.</span></span> <span data-ttu-id="2493a-118">O argumento de `-s` adiciona um SPN depois de não validar nenhuma duplicata.</span><span class="sxs-lookup"><span data-stu-id="2493a-118">The `-s` argument adds a SPN after validating no duplicate exists.</span></span> <span data-ttu-id="2493a-119">**OBSERVAÇÃO: -s** está disponível no Windows Server a partir do Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="2493a-119">**NOTE:-s** is available in Windows Server starting with Windows Server 2008.</span></span>  
  
 <span data-ttu-id="2493a-120">`HTTP` é a classe de serviço.</span><span class="sxs-lookup"><span data-stu-id="2493a-120">`HTTP` is the service class.</span></span> <span data-ttu-id="2493a-121">O serviço Web Servidor de Relatórios é executado em HTTP.SYS.</span><span class="sxs-lookup"><span data-stu-id="2493a-121">The Report Server Web service runs in HTTP.SYS.</span></span> <span data-ttu-id="2493a-122">Uma criação por produto de um SPN para HTTP significa que todos os aplicativos Web no mesmo computador que são executados em HTTP.SYS (incluindo aplicativos hospedados no IIS) receberão tíquetes com base na conta de usuário do domínio.</span><span class="sxs-lookup"><span data-stu-id="2493a-122">A by-product of creating an SPN for HTTP is that all Web applications on the same computer that run in HTTP.SYS (including applications hosted in IIS) will be granted tickets based on the domain user account.</span></span> <span data-ttu-id="2493a-123">Se esses serviços forem executados em uma conta diferente, ocorrerá falha nas solicitações de autenticação.</span><span class="sxs-lookup"><span data-stu-id="2493a-123">If those services run under a different account, the authentication requests will fail.</span></span> <span data-ttu-id="2493a-124">Para evitar esse problema, configure todos os aplicativos HTTP para que sejam executados na mesma conta ou considere a criação de cabeçalhos de host para cada aplicativo e, depois, a criação de SPNs separados para cada cabeçalho de host.</span><span class="sxs-lookup"><span data-stu-id="2493a-124">To avoid this problem, be sure to configure all HTTP applications to run under the same account, or consider creating host headers for each application and then creating separate SPNs for each host header.</span></span> <span data-ttu-id="2493a-125">Quando você configura cabeçalhos de host, é necessário fazer alterações de DNS, independentemente da configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2493a-125">When you configure host headers, DNS changes are required regardless of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] configuration.</span></span>  
  
 <span data-ttu-id="2493a-126">Os valores que você especifica para \<*computername*> , \<*domainname*> e \<*port*> identificam o endereço de rede exclusivo do computador que hospeda o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="2493a-126">The values that you specify for \<*computername*>, \<*domainname*>, and \<*port*> identify the unique network address of the computer that hosts the report server.</span></span> <span data-ttu-id="2493a-127">Pode ser um nome de host local ou um nome de domínio totalmente qualificado (FQDN).</span><span class="sxs-lookup"><span data-stu-id="2493a-127">This can be a local host name or a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="2493a-128">Se você tiver apenas um domínio e estiver usando a porta 80, poderá omitir \<*domainname*> e \<*port*> da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="2493a-128">If you only have one domain and are using port 80, you can omit \<*domainname*> and \<*port*> from your command line.</span></span> <span data-ttu-id="2493a-129">\<*domain-user-account*>é a conta de usuário na qual o serviço servidor de relatório é executado e para o qual o SPN deve ser registrado.</span><span class="sxs-lookup"><span data-stu-id="2493a-129">\<*domain-user-account*> is the user account under which the Report Server service runs and for which the SPN must be registered.</span></span>  
  
## <a name="register-an-spn-for-domain-user-account"></a><span data-ttu-id="2493a-130">Registrar um SPN para a conta de usuário do domínio</span><span class="sxs-lookup"><span data-stu-id="2493a-130">Register an SPN for Domain User Account</span></span>  
  
#### <a name="to-register-an-spn-for-a-report-server-service-running-as-a-domain-user"></a><span data-ttu-id="2493a-131">Para registrar um SPN para um serviço Servidor de Relatório que esteja em execução como um usuário do domínio</span><span class="sxs-lookup"><span data-stu-id="2493a-131">To register an SPN for a Report Server service running as a domain user</span></span>  
  
1.  <span data-ttu-id="2493a-132">Instale o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e configure o serviço Servidor de Relatório para ser executado como uma conta de usuário do domínio.</span><span class="sxs-lookup"><span data-stu-id="2493a-132">Install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and configure the Report Server service to run as a domain user account.</span></span> <span data-ttu-id="2493a-133">Observe que os usuários não poderão se conectar ao servidor de relatório até que você conclua as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="2493a-133">Note that users will not be able to connect to the report server until you complete the following steps.</span></span>  
  
2.  <span data-ttu-id="2493a-134">Faça logon no controlador de domínio como administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="2493a-134">Log on to the domain controller as domain administrator.</span></span>  
  
3.  <span data-ttu-id="2493a-135">Abra uma janela de Prompt de Comando.</span><span class="sxs-lookup"><span data-stu-id="2493a-135">Open a Command Prompt window.</span></span>  
  
4.  <span data-ttu-id="2493a-136">Copie o seguinte comando, substituindo os valores de espaço reservado por valores reais que sejam válidos para sua rede:</span><span class="sxs-lookup"><span data-stu-id="2493a-136">Copy the following command, replacing placeholder values with actual values that are valid for your network:</span></span>  
  
    ```  
    Setspn -s http/<computer-name>.<domain-name>:<port> <domain-user-account>  
    ```  
  
     <span data-ttu-id="2493a-137">Por exemplo: `Setspn -s http/MyReportServer.MyDomain.com:80 MyDomainUser`</span><span class="sxs-lookup"><span data-stu-id="2493a-137">For example: `Setspn -s http/MyReportServer.MyDomain.com:80 MyDomainUser`</span></span>  
  
5.  <span data-ttu-id="2493a-138">Execute o comando.</span><span class="sxs-lookup"><span data-stu-id="2493a-138">Run the command.</span></span>  
  
6.  <span data-ttu-id="2493a-139">Abra o arquivo **RsReportServer.config** e localize a seção `<AuthenticationTypes>` .</span><span class="sxs-lookup"><span data-stu-id="2493a-139">Open the **RsReportServer.config** file and locate the `<AuthenticationTypes>` section.</span></span>  
  
7.  <span data-ttu-id="2493a-140">Adicione `<RSWindowsNegotiate/>` como a primeira entrada desta seção para habilitar NTLM.</span><span class="sxs-lookup"><span data-stu-id="2493a-140">Add `<RSWindowsNegotiate/>` as the first entry in this section to enable NTLM.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2493a-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2493a-141">See Also</span></span>  
 <span data-ttu-id="2493a-142">[Configurar uma conta de serviço &#40;Configuration Manager SSRS&#41;](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="2493a-142">[Configure a Service Account &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="2493a-143">[Configurar a conta de serviço do servidor de relatório &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="2493a-143">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="2493a-144">Gerenciar um servidor de relatórios de Modo Nativo do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2493a-144">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
