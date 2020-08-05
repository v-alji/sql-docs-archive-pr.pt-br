---
title: 'A conexão de dados usa a Autenticação do Windows e não foi possível delegar as credenciais de usuário. As seguintes conexões não foram atualizadas: dados PowerPivot | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d2006df1-d244-4786-b272-49d8996cc88c
author: minewiskan
ms.author: owend
ms.openlocfilehash: be4c61ad4514f3aa4f6f1eda1fe44ad97c4c064f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572252"
---
# <a name="the-data-connection-uses-windows-authentication-and-user-credentials-could-not-be-delegated-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="fdfc7-103">A conexão de dados usa a Autenticação do Windows e não foi possível delegar as credenciais de usuário.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-103">The data connection uses Windows Authentication and user credentials could not be delegated.</span></span> <span data-ttu-id="fdfc7-104">As conexões a seguir não foram atualizadas: Dados PowerPivot</span><span class="sxs-lookup"><span data-stu-id="fdfc7-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="fdfc7-105">Para pastas de trabalho do Excel que contenham dados PowerPivot, os Serviços do Excel retornarão este erro se não conseguirem conectar-se a uma instância de servidor do PowerPivot no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-105">For Excel workbooks that contain PowerPivot data, Excel Services returns this error if it cannot connect to a PowerPivot server instance in SharePoint.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fdfc7-106">Detalhes</span><span class="sxs-lookup"><span data-stu-id="fdfc7-106">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fdfc7-107">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="fdfc7-107">Applies to</span></span>|<span data-ttu-id="fdfc7-108">PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="fdfc7-108">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="fdfc7-109">Versão do produto</span><span class="sxs-lookup"><span data-stu-id="fdfc7-109">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="fdfc7-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdfc7-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="fdfc7-111">Causa</span><span class="sxs-lookup"><span data-stu-id="fdfc7-111">Cause</span></span>|<span data-ttu-id="fdfc7-112">Falha de conexão ao tentar usar um provedor de dados PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-112">Connection failed when attempting to use a PowerPivot data provider.</span></span>|  
|<span data-ttu-id="fdfc7-113">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="fdfc7-113">Message Text</span></span>|<span data-ttu-id="fdfc7-114">A conexão de dados usa a Autenticação do Windows e não foi possível delegar as credenciais de usuário.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-114">The data connection uses Windows Authentication and user credentials could not be delegated.</span></span> <span data-ttu-id="fdfc7-115">As conexões a seguir não foram atualizadas: Dados PowerPivot</span><span class="sxs-lookup"><span data-stu-id="fdfc7-115">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fdfc7-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="fdfc7-116">Explanation</span></span>  
 <span data-ttu-id="fdfc7-117">Há várias causas para essa mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-117">There are multiple causes for this error message.</span></span> <span data-ttu-id="fdfc7-118">O fator comum por trás de todas elas é que os Serviços do Excel não podem obter uma identidade do usuário do Windows válida de um token de declarações no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-118">The common factor behind all of them is that Excel Services cannot get a valid Windows user identity from a claims token in SharePoint.</span></span> <span data-ttu-id="fdfc7-119">No caso de pastas de trabalho do Excel que contenham dados PowerPivot, esse erro ocorre quando uma destas condições existe:</span><span class="sxs-lookup"><span data-stu-id="fdfc7-119">In the case of Excel workbooks that contain PowerPivot data, this error occurs when any of the following conditions exist:</span></span>  
  
-   <span data-ttu-id="fdfc7-120">O Claims para Windows Token Service não está em execução.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-120">The Claims to Windows Token Service is not running.</span></span> <span data-ttu-id="fdfc7-121">Você pode confirmar a causa desse erro exibindo o arquivo de log do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-121">You can confirm the cause of this error by viewing the SharePoint log file.</span></span> <span data-ttu-id="fdfc7-122">Se os logs do SharePoint incluírem a mensagem "Não foi possível localizar o ponto de extremidade de pipe 'net.pipe://localhost/s 4u/022694f3-9fbd-422b-b4b2-312e25dae2a2' em sua máquina local", o Claims para Windows Token Service não está em execução.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-122">If the SharePoint logs include the message "The pipe endpoint 'net.pipe://localhost/s4u/022694f3-9fbd-422b-b4b2-312e25dae2a2' could not be found on your local machine", the Claims to Windows Token Service is not running.</span></span> <span data-ttu-id="fdfc7-123">Para iniciá-lo, use a Administração Central e verifique se o serviço está sendo executado no aplicativo de console de Serviços.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-123">To start it, use Central Administration and then verify the service is running in the Services console application.</span></span>  
  
-   <span data-ttu-id="fdfc7-124">Um controlador de domínio não está disponível para validar a identidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-124">A domain controller is not available to validate the user identity.</span></span> <span data-ttu-id="fdfc7-125">O Claims to Windows Token Service não usa credenciais armazenadas em cache.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-125">The Claims to Windows Token Service does not use cached credentials.</span></span> <span data-ttu-id="fdfc7-126">Valida a identidade do usuário para cada conexão.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-126">It validates the user identity for each connection.</span></span> <span data-ttu-id="fdfc7-127">Você pode confirmar a causa desse erro exibindo o arquivo de log do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-127">You can confirm the cause of this error by viewing the SharePoint log file.</span></span> <span data-ttu-id="fdfc7-128">Se os logs do SharePoint incluírem a mensagem "Falha ao obter WindowsIdentity de IClaimsIdentity", não foi possível autenticar a identidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-128">If the SharePoint logs include the message "Failed to get WindowsIdentity from IClaimsIdentity", the user identity could not be authenticated.</span></span>  
  
-   <span data-ttu-id="fdfc7-129">Os computadores devem ser membros do mesmo domínio ou de domínios que tenham uma relação de confiança bidirecional.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-129">The computers must be members of the same domain or in domains that have a two-way trust relationship.</span></span>  
  
-   <span data-ttu-id="fdfc7-130">Você deve usar contas de usuário de domínio do Windows.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-130">You must use Windows domain user accounts.</span></span> <span data-ttu-id="fdfc7-131">As contas devem ter um UPN.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-131">The accounts must have a Universal Principal Name (UPN).</span></span>  
  
-   <span data-ttu-id="fdfc7-132">A conta de serviço dos Serviços do Excel deve ter permissões do Active Directory para consultar o objeto.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-132">The Excel Services service account must have Active Directory permissions to query the object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fdfc7-133">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="fdfc7-133">User Action</span></span>  
 <span data-ttu-id="fdfc7-134">Use as instruções a seguir para verificar o status do Claims para Windows Token Service.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-134">Use the following instructions to check the status of the Claims to Windows Token Service.</span></span>  
  
 <span data-ttu-id="fdfc7-135">Para todos os outros cenários, consulte o administrador da rede.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-135">For all other scenarios, check with your network administrator.</span></span>  
  
#### <a name="enable-claims-to-windows-token-service"></a><span data-ttu-id="fdfc7-136">Habilitar o Claims para Windows Token Service</span><span class="sxs-lookup"><span data-stu-id="fdfc7-136">Enable Claims to Windows Token Service</span></span>  
  
1.  <span data-ttu-id="fdfc7-137">Na administração central, em configurações do sistema, clique em **gerenciar serviços no servidor**.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-137">In Central Administration, in System Settings, click **Manage services on server**.</span></span>  
  
2.  <span data-ttu-id="fdfc7-138">Selecione **Claims para Windows Token Service**e clique em **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-138">Select **Claims to Windows Token Service**, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="fdfc7-139">Verifique se o serviço também está em execução no console Serviços:</span><span class="sxs-lookup"><span data-stu-id="fdfc7-139">Verify the service is also running in the Services console:</span></span>  
  
    1.  <span data-ttu-id="fdfc7-140">Em Ferramentas Administrativas, clique em Serviços.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-140">In Administrative Tools, click Services.</span></span>  
  
    2.  <span data-ttu-id="fdfc7-141">Inicie o Claims to Windows Token Service se ele ainda não estiver em execução.</span><span class="sxs-lookup"><span data-stu-id="fdfc7-141">Start the Claims to Windows Token Service if it is not running.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdfc7-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fdfc7-142">See Also</span></span>  
 [<span data-ttu-id="fdfc7-143">Configurar contas de serviço PowerPivot</span><span class="sxs-lookup"><span data-stu-id="fdfc7-143">Configure PowerPivot Service Accounts</span></span>](configure-power-pivot-service-accounts.md)  
  
  
