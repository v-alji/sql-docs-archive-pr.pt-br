---
title: Autorização no Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- authorization [Reporting Services]
ms.assetid: 15fc1c7b-560c-4737-b126-e0d428a1b530
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7420b45175ca0b0a5fc66da4a7939b07b79c75b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574520"
---
# <a name="authorization-in-reporting-services"></a><span data-ttu-id="d4641-102">Autorização no Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d4641-102">Authorization in Reporting Services</span></span>
  <span data-ttu-id="d4641-103">Autorização é o processo de determinar se uma identidade deve receber o tipo de acesso solicitado a um determinado recurso no banco de dados de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="d4641-103">Authorization is the process of determining whether an identity should be granted the requested type of access to a given resource in the report server database.</span></span> <span data-ttu-id="d4641-104">O [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] usa uma arquitetura de autorização baseada em função que concede um acesso de usuário a um determinado recurso com base na atribuição de função do usuário para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d4641-104">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses a role-based authorization architecture that grants a user access to a given resource based on the user's role assignment for the application.</span></span> <span data-ttu-id="d4641-105">As extensões de segurança para o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] contêm uma implementação de um componente de autorização usado para conceder acesso a usuários assim que eles se autenticam no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="d4641-105">Security extensions for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] contain an implementation of an authorization component that is used to grant access to users once they are authenticated on the report server.</span></span> <span data-ttu-id="d4641-106">A autorização é invocada quando um usuário tenta executar uma operação no sistema ou um item de servidor de relatório por meio da API SOAP e via acesso à URL.</span><span class="sxs-lookup"><span data-stu-id="d4641-106">Authorization is invoked when a user attempts to perform an operation on the system or a report server item through the SOAP API and via URL access.</span></span> <span data-ttu-id="d4641-107">Isso é possível por meio da interface de extensão de segurança **IAuthorizationExtension**.</span><span class="sxs-lookup"><span data-stu-id="d4641-107">This is made possible through the security extension interface **IAuthorizationExtension**.</span></span> <span data-ttu-id="d4641-108">Como foi dito anteriormente, todas as extensões herdam de **IExtension** , a interface base para qualquer extensão que você implanta.</span><span class="sxs-lookup"><span data-stu-id="d4641-108">As stated previously, all extensions inherit from **IExtension** the base interface for any extension that you deploy.</span></span> <span data-ttu-id="d4641-109">**IExtension** e **IAuthorizationExtension** são os membros do namespace **Microsoft.ReportingServices.Interfaces** .</span><span class="sxs-lookup"><span data-stu-id="d4641-109">**IExtension** and **IAuthorizationExtension** are members of the **Microsoft.ReportingServices.Interfaces** namespace.</span></span>

## <a name="checking-access"></a><span data-ttu-id="d4641-110">Verificando o acesso</span><span class="sxs-lookup"><span data-stu-id="d4641-110">Checking Access</span></span>
 <span data-ttu-id="d4641-111">Em autorização, a chave para qualquer implementação de segurança personalizada é a verificação de acesso, que é implementada no método <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4641-111">In authorization, the key to any custom security implementation is the access check, which is implemented in the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method.</span></span> <span data-ttu-id="d4641-112"><xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> é chamado a cada vez que um usuário tenta uma operação no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="d4641-112"><xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> is called each time a user attempts an operation on the report server.</span></span> <span data-ttu-id="d4641-113">O método <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> é sobrecarregado para cada tipo de operação.</span><span class="sxs-lookup"><span data-stu-id="d4641-113">The <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method is overloaded for each operation type.</span></span> <span data-ttu-id="d4641-114">Para operações de pasta, um exemplo de uma verificação de acesso poderia ficar assim:</span><span class="sxs-lookup"><span data-stu-id="d4641-114">For folder operations, an example of an access check might look like the following:</span></span>

```
// Overload for Folder operations
public bool CheckAccess(
   string userName, 
   IntPtr userToken, 
   byte[] secDesc, 
   FolderOperation requiredOperation)
{
   // If the user is the administrator, allow unrestricted access.
   if (userName == m_adminUserName) 
      return true;

   AceCollection acl = DeserializeAcl(secDesc);
   foreach(AceStruct ace in acl)
   {
         if (userName == ace.PrincipalName)
         {
            foreach(FolderOperation aclOperation in 
               ace.FolderOperations)
            {
               if (aclOperation == requiredOperation)
                     return true;
            }
         }
   }
   return false;
}
```

 <span data-ttu-id="d4641-115">O servidor de relatório chama o método <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> passando o nome do usuário conectado, um token de usuário, o descritor de segurança para o item e a operação solicitada.</span><span class="sxs-lookup"><span data-stu-id="d4641-115">The report server calls the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method by passing in the name of the logged-on user, a user token, the security descriptor for the item, and the requested operation.</span></span> <span data-ttu-id="d4641-116">Aqui você poderia verificar o descritor de segurança para o nome de usuário e a permissão apropriada para concluir a solicitação, retornar `true` para mostrar que o acesso foi concedido ou `false` para mostrar que o acesso foi negado.</span><span class="sxs-lookup"><span data-stu-id="d4641-116">Here you would check the security descriptor for the user name and the appropriate permission to complete the request, then return `true` to signify that access is granted or `false` to signify access is denied.</span></span>

## <a name="security-descriptors"></a><span data-ttu-id="d4641-117">Descritores de segurança</span><span class="sxs-lookup"><span data-stu-id="d4641-117">Security Descriptors</span></span>
 <span data-ttu-id="d4641-118">Ao definir políticas de autorização em itens do banco de dados do servidor de relatório, um aplicativo cliente (como o Gerenciador de Relatórios) envia as informações do usuário na extensão de segurança junto com a política de segurança do item.</span><span class="sxs-lookup"><span data-stu-id="d4641-118">When setting authorization policies on items in the report server database, a client application (such as Report Manager) submits the user information to the security extension along with a security policy for the item.</span></span> <span data-ttu-id="d4641-119">Essa política de segurança e as informações do usuário são conhecidas coletivamente como um descritor de segurança.</span><span class="sxs-lookup"><span data-stu-id="d4641-119">This security policy and user information are known collectively as a security descriptor.</span></span> <span data-ttu-id="d4641-120">Um descritor de segurança contém as seguintes informações para um item no banco de dados do servidor de relatório:</span><span class="sxs-lookup"><span data-stu-id="d4641-120">A security descriptor contains the following information for an item in the report server database:</span></span>

-   <span data-ttu-id="d4641-121">O grupo ou o usuário com algum tipo de permissão para executar operações no item.</span><span class="sxs-lookup"><span data-stu-id="d4641-121">The group or user that has some type of permission to perform operations on the item.</span></span>

-   <span data-ttu-id="d4641-122">O tipo do item.</span><span class="sxs-lookup"><span data-stu-id="d4641-122">The item's type.</span></span>

-   <span data-ttu-id="d4641-123">Uma lista de controle de acesso discricionário que controla acesso ao item.</span><span class="sxs-lookup"><span data-stu-id="d4641-123">A discretionary access control list controlling access to the item.</span></span>

 <span data-ttu-id="d4641-124">Os descritores de segurança são criados por meio do serviço Web <xref:ReportService2010.ReportingService2010.SetPolicies%2A> e dos métodos <xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4641-124">Security descriptors are created using the Web service <xref:ReportService2010.ReportingService2010.SetPolicies%2A> and <xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A> methods.</span></span>

### <a name="authorization-flow"></a><span data-ttu-id="d4641-125">Fluxo de autorização</span><span class="sxs-lookup"><span data-stu-id="d4641-125">Authorization Flow</span></span>
 <span data-ttu-id="d4641-126">A autorização do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] é controlada pela extensão de segurança configurada para ser executada atualmente no servidor.</span><span class="sxs-lookup"><span data-stu-id="d4641-126">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] authorization is controlled by the security extension currently configured to run on the server.</span></span> <span data-ttu-id="d4641-127">A autorização é baseada em função e está limitada às permissões e operações fornecidas pela arquitetura de segurança do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d4641-127">Authorization is role-based and limited to the permissions and operations supplied by the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security architecture.</span></span> <span data-ttu-id="d4641-128">O diagrama a seguir descreve o processo de autorização de usuários a operar em itens no banco de dados do servidor de relatório:</span><span class="sxs-lookup"><span data-stu-id="d4641-128">The following diagram depicts the process of authorizing users to operate on items in the report server database:</span></span>

 <span data-ttu-id="d4641-129">![Fluxo de autorização de segurança do Reporting Services](../../media/rosettasecurityextensionauthorizationflow.gif "Fluxo de autorização de segurança do Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="d4641-129">![Reporting Services security authorization flow](../../media/rosettasecurityextensionauthorizationflow.gif "Reporting Services security authorization flow")</span></span>

 <span data-ttu-id="d4641-130">Como mostrado neste diagrama, a autorização segue esta sequência:</span><span class="sxs-lookup"><span data-stu-id="d4641-130">As shown in this diagram, authorization follows this sequence:</span></span>

1.  <span data-ttu-id="d4641-131">Uma vez autenticados, os aplicativos cliente fazem solicitações ao servidor de relatório por meio dos métodos do serviço Web Servidor de Relatório.</span><span class="sxs-lookup"><span data-stu-id="d4641-131">Once authenticated, client applications make requests to the report server through the Reporting Services Web service methods.</span></span> <span data-ttu-id="d4641-132">Um tíquete de autenticação é passado ao servidor de relatório na forma de um cookie no cabeçalho HTTP de cada solicitação Web.</span><span class="sxs-lookup"><span data-stu-id="d4641-132">An authentication ticket is passed to the report server in the form of a cookie in the HTTP header of each Web request.</span></span>

2.  <span data-ttu-id="d4641-133">O cookie é validado antes de qualquer verificação de acesso.</span><span class="sxs-lookup"><span data-stu-id="d4641-133">The cookie is validated prior to any access check.</span></span>

3.  <span data-ttu-id="d4641-134">Após a validação do cookie, o servidor de relatório chama <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension.GetUserInfo%2A> e o usuário recebe uma identidade.</span><span class="sxs-lookup"><span data-stu-id="d4641-134">Once the cookie is validated, the report server calls <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension.GetUserInfo%2A> and the user is given an identity.</span></span>

4.  <span data-ttu-id="d4641-135">O usuário tenta executar uma operação por meio do serviço Web Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d4641-135">The user attempts an operation through the Reporting Services Web service.</span></span>

5.  <span data-ttu-id="d4641-136">O servidor de relatório chama o método <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4641-136">The report server calls the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method.</span></span>

6.  <span data-ttu-id="d4641-137">O descritor de segurança é recuperado e passado a uma implementação de extensão de segurança personalizada de <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4641-137">The security descriptor is retrieved and passed to a custom security extension implementation of <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span></span> <span data-ttu-id="d4641-138">Neste ponto, o usuário, grupo ou computador é comparado ao descritor de segurança do item acessado e é autorizado a executar a operação solicitada.</span><span class="sxs-lookup"><span data-stu-id="d4641-138">At this point, the user, group, or computer is compared to the security descriptor of the item being accessed and is authorized to perform the requested operation.</span></span>

7.  <span data-ttu-id="d4641-139">Se o usuário for autorizado, o serviço Web executará a operação e devolverá uma resposta ao aplicativo de chamada.</span><span class="sxs-lookup"><span data-stu-id="d4641-139">If the user is authorized, the Web service performs the operation and returns a response to the calling application.</span></span>


