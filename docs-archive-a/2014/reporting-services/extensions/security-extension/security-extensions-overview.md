---
title: Visão geral das extensões de segurança | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], extensions
ms.assetid: 24ccd795-6506-457c-93ac-6a9dd6bb9a46
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9cd6c2a1518b724a7faafecdb2926505694e9707
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574513"
---
# <a name="security-extensions-overview"></a><span data-ttu-id="81452-102">Visão geral de extensões de segurança</span><span class="sxs-lookup"><span data-stu-id="81452-102">Security Extensions Overview</span></span>
  <span data-ttu-id="81452-103">Uma extensão de segurança do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] habilita a autenticação e a autorização de usuários ou grupos; ou seja, ela permite que diferentes usuários façam logon em um servidor de relatório e, com base em suas identidades, executem diferentes tarefas ou operações.</span><span class="sxs-lookup"><span data-stu-id="81452-103">A [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security extension enables the authentication and authorization of users or groups; that is, it enables different users to log on to a report server and, based on their identities, perform different tasks or operations.</span></span> <span data-ttu-id="81452-104">Por padrão, o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] usa uma extensão de autenticação baseada no Windows, que usa protocolos de contas do Windows para verificar as identidades de usuários que afirmam ter contas no sistema.</span><span class="sxs-lookup"><span data-stu-id="81452-104">By default, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses a Windows-based authentication extension, which uses Windows account protocols to verify the identities of users who claim to have accounts on the system.</span></span> <span data-ttu-id="81452-105">O [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] usa um sistema de segurança baseado em função para autorizar usuários.</span><span class="sxs-lookup"><span data-stu-id="81452-105">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses a role-based security system to authorize users.</span></span> <span data-ttu-id="81452-106">O modelo de segurança baseada em função do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] é semelhante aos modelos de segurança baseada em função de outras tecnologias.</span><span class="sxs-lookup"><span data-stu-id="81452-106">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] role-based security model is similar to the role-based security models of other technologies.</span></span>

 <span data-ttu-id="81452-107">Como extensões de segurança se baseiam em uma API aberta e extensível, você pode criar autenticação nova e extensões de autorização no [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81452-107">Because security extensions are based on an open and extensible API, you can create new authentication and authorization extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="81452-108">Este é um exemplo de implementação de extensão de segurança típica que usa a autenticação baseada em formulários e a autorização:</span><span class="sxs-lookup"><span data-stu-id="81452-108">The following is an example of a typical security extension implementation that uses Forms-based authentication and authorization:</span></span>

 <span data-ttu-id="81452-109">![Processo de extensão de segurança do Reporting Services](../../media/rosettasecurityextensionflow.gif "Processo de extensão de segurança do Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="81452-109">![Reporting Services security extension process](../../media/rosettasecurityextensionflow.gif "Reporting Services security extension process")</span></span>

 <span data-ttu-id="81452-110">Conforme mostrado na ilustração, a autenticação e a autorização ocorrem desta forma:</span><span class="sxs-lookup"><span data-stu-id="81452-110">As shown in the illustration, authentication and authorization occur as follows:</span></span>

1.  <span data-ttu-id="81452-111">Um usuário tenta acessar o Gerenciador de Relatórios usando uma URL e é redirecionado para um formulário que coleta credenciais de usuário para o aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="81452-111">A user tries to access Report Manager by using a URL and is redirected to a form that collects user credentials for the client application.</span></span>

2.  <span data-ttu-id="81452-112">O usuário submete credenciais ao formulário.</span><span class="sxs-lookup"><span data-stu-id="81452-112">The user submits credentials to the form.</span></span>

3.  <span data-ttu-id="81452-113">As credenciais de usuário são submetidas ao serviço Web do Reporting Services através do método <xref:ReportService2010.ReportingService2010.LogonUser%2A>.</span><span class="sxs-lookup"><span data-stu-id="81452-113">The user credentials are submitted to the Reporting Services Web service through the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method.</span></span>

4.  <span data-ttu-id="81452-114">O serviço Web chama a extensão de segurança fornecida pelo cliente e verifica se há nome e senha do usuário na autoridade de segurança personalizada.</span><span class="sxs-lookup"><span data-stu-id="81452-114">The Web service calls the customer-supplied security extension and verifies that the user name and password exist in the custom security authority.</span></span>

5.  <span data-ttu-id="81452-115">Após a autenticação, o serviço Web cria um tíquete de autenticação (conhecido como "cookie"), gerencia o tíquete e verifica a função do usuário para a página inicial do Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="81452-115">After authentication, the Web service creates an authentication ticket (known as a "cookie"), manages the ticket, and verifies the user's role for the Home page of Report Manager.</span></span>

6.  <span data-ttu-id="81452-116">O serviço Web devolve o cookie ao navegador e exibe a interface de usuário apropriada no Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="81452-116">The Web service returns the cookie to the browser and displays the appropriate user interface in Report Manager.</span></span>

7.  <span data-ttu-id="81452-117">Depois da autenticação do usuário, o navegador faz solicitações ao Gerenciador de Relatórios enquanto transmite o cookie no cabeçalho HTTP.</span><span class="sxs-lookup"><span data-stu-id="81452-117">After the user is authenticated, the browser makes requests to Report Manager while transmitting the cookie in the HTTP header.</span></span> <span data-ttu-id="81452-118">Essas solicitações são uma resposta a ações do usuário dentro do aplicativo Gerenciador de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="81452-118">These requests are in response to user actions within the Report Manager application.</span></span>

8.  <span data-ttu-id="81452-119">O cookie é transmitido no cabeçalho HTTP para o serviço Web junto com a operação de usuário solicitada.</span><span class="sxs-lookup"><span data-stu-id="81452-119">The cookie is transmitted in the HTTP header to the Web service along with the requested user operation.</span></span>

9. <span data-ttu-id="81452-120">O cookie é validado; quando ele é válido, o servidor de relatório retorna o descritor de segurança e outras informações sobre a operação solicitada do banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="81452-120">The cookie is validated, and if it is valid, the report server returns the security descriptor and other information relating to the requested operation from the report server database.</span></span>

10. <span data-ttu-id="81452-121">Quando o cookie é válido, o servidor de relatório faz uma chamada à extensão de segurança para verificar se o usuário está autorizado a executar a operação específica.</span><span class="sxs-lookup"><span data-stu-id="81452-121">If the cookie is valid, the report server makes a call to the security extension to check if the user is authorized to perform the specific operation.</span></span>

11. <span data-ttu-id="81452-122">Se o usuário estiver autorizado, o servidor de relatório executará a operação solicitada e retornará o controle ao chamador.</span><span class="sxs-lookup"><span data-stu-id="81452-122">If the user is authorized, the report server performs the requested operation and returns control to the caller.</span></span>

12. <span data-ttu-id="81452-123">Depois da autenticação do usuário, o acesso de URL ao servidor de relatório usa o mesmo cookie.</span><span class="sxs-lookup"><span data-stu-id="81452-123">After the user is authenticated, URL access to the report server uses the same cookie.</span></span> <span data-ttu-id="81452-124">O cookie é transmitido no cabeçalho HTTP.</span><span class="sxs-lookup"><span data-stu-id="81452-124">The cookie is transmitted in the HTTP header.</span></span>

13. <span data-ttu-id="81452-125">O usuário continua solicitando operações no servidor de relatório até o término da sessão.</span><span class="sxs-lookup"><span data-stu-id="81452-125">The user continues to request operations on the report server until the session has ended.</span></span>

## <a name="when-to-implement-a-security-extension"></a><span data-ttu-id="81452-126">Quando implementar uma extensão de segurança</span><span class="sxs-lookup"><span data-stu-id="81452-126">When to Implement a Security Extension</span></span>
 <span data-ttu-id="81452-127">É recomendável usar a Autenticação do Windows quando isso é possível.</span><span class="sxs-lookup"><span data-stu-id="81452-127">We recommend that you use Windows Authentication if at all possible.</span></span> <span data-ttu-id="81452-128">Porém, a autenticação personalizada e a autorização do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] podem ser apropriadas nestes dois casos:</span><span class="sxs-lookup"><span data-stu-id="81452-128">However, custom authentication and authorization for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] may be appropriate in the following two cases:</span></span>

-   <span data-ttu-id="81452-129">Você tem um aplicativo Internet ou extranet que não pode usar contas do Windows.</span><span class="sxs-lookup"><span data-stu-id="81452-129">You have an Internet or extranet application that cannot use Windows accounts.</span></span>

-   <span data-ttu-id="81452-130">Você tem usuários e funções com definição personalizada e precisa fornecer um esquema de autorização compatível no [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81452-130">You have custom-defined users and roles and need to provide a matching authorization scheme in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="81452-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="81452-131">See Also</span></span>
 <span data-ttu-id="81452-132">[Implementando uma extensão de segurança](../security-extension/implementing-a-security-extension.md) [Configurar Report Manager para passar cookies de autenticação personalizados](../../security/configure-the-web-portal-to-pass-custom-authentication-cookies.md)</span><span class="sxs-lookup"><span data-stu-id="81452-132">[Implementing a Security Extension](../security-extension/implementing-a-security-extension.md) [Configure Report Manager to Pass Custom Authentication Cookies](../../security/configure-the-web-portal-to-pass-custom-authentication-cookies.md)</span></span>


