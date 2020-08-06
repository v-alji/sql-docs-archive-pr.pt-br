---
title: Autenticação do serviço Web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], authentication
- XML Web service [Reporting Services], authentication
- Report Server Web service, authentication
ms.assetid: 852b4947-a090-4e54-8555-5a503945ceab
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0c7836d6eba8c6ab3f0a8e705ebb79c7ed73eb17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684488"
---
# <a name="web-service-authentication"></a><span data-ttu-id="6e9d5-102">Autenticação de serviço Web</span><span class="sxs-lookup"><span data-stu-id="6e9d5-102">Web Service Authentication</span></span>
  <span data-ttu-id="6e9d5-103">Você pode usar a Autenticação de Windows ou a autenticação Básica para autenticar as chamadas feitas ao serviço Web Servidor de Relatório.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-103">You can use either Windows Authentication or Basic authentication to authenticate the calls made to the Report Server Web service.</span></span> <span data-ttu-id="6e9d5-104">Qualquer cliente que faz solicitações SOAP ao servidor de relatório deve implementar a parte cliente de um dos protocolos de autenticação suportados.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-104">Any client that makes SOAP requests to the report server must implement the client portion of one of the supported authentication protocols.</span></span> <span data-ttu-id="6e9d5-105">Se você estiver usando o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] , poderá usar as classes http de código gerenciado para implementar a autenticação.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-105">If you are using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], you can use the managed code HTTP classes to implement authentication.</span></span> <span data-ttu-id="6e9d5-106">O uso dessas APIs facilita o envio de informações de autenticação junto comas solicitações SOAP.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-106">Using these APIs makes it easy to send authentication information along with the SOAP requests.</span></span>  
  
 <span data-ttu-id="6e9d5-107">Se você não tiver as credenciais apropriados antes de fazer uma chamada ao serviço Web Servidor de Relatório, a chamada falhará.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-107">If you do not have appropriate credentials before you make a call to the Report Server Web service, the call fails.</span></span> <span data-ttu-id="6e9d5-108">Em tempo de execução, passe as credenciais para o serviço Web definindo a propriedade **Credentials** do objeto do lado do cliente que representa o serviço Web antes de chamar seus métodos.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-108">At run time, you can pass credentials to the Web service by setting the **Credentials** property of the client-side object that represents the Web service before you call its methods.</span></span>  
  
 <span data-ttu-id="6e9d5-109">As seções a seguir contêm código de exemplo que envia credenciais usando o [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e9d5-109">The following sections contain example code that sends credentials using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="windows-authentication"></a><span data-ttu-id="6e9d5-110">Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="6e9d5-110">Windows Authentication</span></span>  
 <span data-ttu-id="6e9d5-111">O código a seguir transmite credenciais do Windows ao serviço Web.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-111">The following code passes Windows credentials to the Web service.</span></span>  
  
```vb  
Dim rs As New ReportingService()  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
```  
  
```csharp  
ReportingService rs = new ReportingService();  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
```  
  
## <a name="basic-authentication"></a><span data-ttu-id="6e9d5-112">Autenticação Básica</span><span class="sxs-lookup"><span data-stu-id="6e9d5-112">Basic Authentication</span></span>  
 <span data-ttu-id="6e9d5-113">O código a seguir transmite credenciais Básicas ao serviço Web.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-113">The following code passes Basic credentials to the Web service.</span></span>  
  
```vb  
Dim rs As New ReportingService()  
rs.Credentials = New System.Net.NetworkCredential("username", "password", "domain")  
```  
  
```csharp  
ReportingService service = new ReportingService();  
service.Credentials = new System.Net.NetworkCredential("username", "password", "domain");  
```  
  
 <span data-ttu-id="6e9d5-114">As credenciais devem ser definidas antes de você chamar qualquer um dos métodos do serviço Web Servidor de Relatório.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-114">The credentials must be set before you call any of the methods of the Report Server Web service.</span></span> <span data-ttu-id="6e9d5-115">Se você não definir as credenciais, receberá o código de erro HTTP 401 Erro: acesso negado.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-115">If you do not set the credentials, you receive the error code an HTTP 401 Error: Access Denied.</span></span> <span data-ttu-id="6e9d5-116">Autentique o serviço antes de usá-lo, mas depois de definir as credenciais; não será preciso defini-las novamente, desde que você continue usando a mesma variável de serviço (como *rs*).</span><span class="sxs-lookup"><span data-stu-id="6e9d5-116">You must authenticate the service before you use it, but after you have set the credentials, you do not need to set them again as long as you continue to use the same service variable (such as *rs*).</span></span>  
  
## <a name="custom-authentication"></a><span data-ttu-id="6e9d5-117">Autenticação personalizada</span><span class="sxs-lookup"><span data-stu-id="6e9d5-117">Custom Authentication</span></span>  
 <span data-ttu-id="6e9d5-118">O [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] inclui uma API de programação que oferece aos desenvolvedores a oportunidade de criar e de desenvolver extensões de autenticação personalizadas, conhecido como extensões de segurança.</span><span class="sxs-lookup"><span data-stu-id="6e9d5-118">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] includes a programming API that provides developers with the opportunity to design and develop custom authentication extensions, known as security extensions.</span></span> <span data-ttu-id="6e9d5-119">Para obter mais informações, consulte [Implementing a Security Extension](../../extensions/security-extension/implementing-a-security-extension.md).</span><span class="sxs-lookup"><span data-stu-id="6e9d5-119">For more information, see [Implementing a Security Extension](../../extensions/security-extension/implementing-a-security-extension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e9d5-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6e9d5-120">See Also</span></span>  
 <span data-ttu-id="6e9d5-121">[Criando aplicativos usando o serviço Web e o .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="6e9d5-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="6e9d5-122">Serviço Web do Servidor de Relatório</span><span class="sxs-lookup"><span data-stu-id="6e9d5-122">Report Server Web Service</span></span>](../report-server-web-service.md)  
  
  
