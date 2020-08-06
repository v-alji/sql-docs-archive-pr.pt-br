---
title: Como executar o assistente de análise do supervisor de atualização | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor Analysis Wizard
ms.assetid: d7d2a1e2-1179-4c05-9b0f-555b04dd1199
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7c3e5e8a52c3b166b076aedb122e68f860037edf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582789"
---
# <a name="how-to-run-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="592b2-102">Como fazer: Para executar o Assistente para Análise do Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="592b2-102">How to: Run the Upgrade Advisor Analysis Wizard</span></span>
  <span data-ttu-id="592b2-103">Você inicia o Assistente para Análise do Supervisor de Atualização na página inicial do Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="592b2-103">You start the Upgrade Advisor Analysis Wizard from the Upgrade Advisor start page.</span></span> <span data-ttu-id="592b2-104">Este tópico descreve como executar o Assistente para Análise do Supervisor de Atualização.</span><span class="sxs-lookup"><span data-stu-id="592b2-104">This topic describes how to run the Upgrade Advisor Analysis Wizard.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="592b2-105">Quando você executa o Assistente para Análise do Supervisor de Atualização, o Supervisor de Atualização salva os relatórios na pasta de relatórios padrão.</span><span class="sxs-lookup"><span data-stu-id="592b2-105">When you run the Upgrade Advisor Analysis Wizard, Upgrade Advisor saves the reports in the default report folder.</span></span> <span data-ttu-id="592b2-106">Entretanto, o visualizador de relatórios exibe apenas os cinco relatórios mais recentes salvos.</span><span class="sxs-lookup"><span data-stu-id="592b2-106">However, the report viewer displays only the five latest saved reports.</span></span> <span data-ttu-id="592b2-107">O local padrão dos relatórios é meus documentos \\ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] upgrade Advisor\110\Reports.</span><span class="sxs-lookup"><span data-stu-id="592b2-107">The default location for the reports is My Documents\\[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor\110\Reports.</span></span>  
  
### <a name="to-run-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="592b2-108">Para executar o assistente de análise do supervisor de atualização</span><span class="sxs-lookup"><span data-stu-id="592b2-108">To run the Upgrade Advisor Analysis Wizard</span></span>  
  
1.  <span data-ttu-id="592b2-109">Na página inicial do supervisor de atualização, clique em **Iniciar assistente de análise do supervisor de atualização**.</span><span class="sxs-lookup"><span data-stu-id="592b2-109">On the Upgrade Advisor start page, click **Launch Upgrade Advisor Analysis Wizard**.</span></span>  
  
2.  <span data-ttu-id="592b2-110">Na página \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] componentes\*\* , digite o nome do servidor a ser verificado na caixa **nome do servidor** e clique em **detectar**.</span><span class="sxs-lookup"><span data-stu-id="592b2-110">On the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components** page, enter the name of the server to scan in the **Server name** box, and then click **Detect**.</span></span> <span data-ttu-id="592b2-111">Use as políticas a seguir para o nome de servidor:</span><span class="sxs-lookup"><span data-stu-id="592b2-111">Use the following guidelines for the server name:</span></span>  
  
    -   <span data-ttu-id="592b2-112">Para verificar instâncias não clusterizadas, insira o nome do computador.</span><span class="sxs-lookup"><span data-stu-id="592b2-112">To scan nonclustered instances, enter the computer name.</span></span>  
  
    -   <span data-ttu-id="592b2-113">Para verificar instâncias clusterizadas, digite o nome do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual.</span><span class="sxs-lookup"><span data-stu-id="592b2-113">To scan clustered instances, enter the virtual [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] name.</span></span>  
  
    -   <span data-ttu-id="592b2-114">Para verificar os componentes não clusterizados que estão instalados em um nó de um cluster, insira o nome do nó.</span><span class="sxs-lookup"><span data-stu-id="592b2-114">To scan nonclustered components that are installed on a node of a cluster, enter the node name.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="592b2-115">O Supervisor de Atualização não oferece suporte à conexão a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que não é definida para usar a porta padrão (1433) para conexões de cliente.</span><span class="sxs-lookup"><span data-stu-id="592b2-115">Upgrade Advisor does not support connecting to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is not set to use the standard port (1433) for client connections.</span></span> <span data-ttu-id="592b2-116">Se você desejar se conectar a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que não usa a porta padrão (1433), crie um alias usando o endereço IP e a porta.</span><span class="sxs-lookup"><span data-stu-id="592b2-116">If you want to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that does not use the standard port (1433), create an alias using the IP address and the port.</span></span> <span data-ttu-id="592b2-117">Para obter mais informações sobre como configurar protocolos de cliente e criar um alias para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instâncias, consulte [Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="592b2-117">For more information about configuring client protocols and creating an alias for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances, see [Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md).</span></span>  
    >   
    >  <span data-ttu-id="592b2-118">Se você não tiver [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalado no computador no qual está executando o supervisor de atualização, clique em **Iniciar**e em executar `cliconfg` .</span><span class="sxs-lookup"><span data-stu-id="592b2-118">If you do not have [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on the computer on which you are running Upgrade Advisor, click **Start**, and then run  `cliconfg`.</span></span> <span data-ttu-id="592b2-119">Isso abre a caixa de diálogo \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utilitário de rede do cliente\*\* .</span><span class="sxs-lookup"><span data-stu-id="592b2-119">This opens the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client Network Utility** dialog box.</span></span> <span data-ttu-id="592b2-120">Use a guia **alias** para criar o alias.</span><span class="sxs-lookup"><span data-stu-id="592b2-120">Use the **Alias** tab to create the alias.</span></span>  
  
3.  <span data-ttu-id="592b2-121">Examine a lista de componentes detectados, modifique as seleções conforme necessário e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592b2-121">Review the list of components detected, modify the selections as necessary, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="592b2-122">Na página **parâmetros de conexão** , selecione a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que você deseja verificar, selecione o método de autenticação e, se necessário, insira informações de nome de usuário e senha e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="592b2-122">On the **Connection Parameters** page, select the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you want to scan, select the authentication method and, if necessary, enter user name and password information, and then click **Next**.</span></span>  
  
     <span data-ttu-id="592b2-123">O nome de instância padrão é MSSQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="592b2-123">The default instance name is MSSQLSERVER.</span></span>  
  
5.  <span data-ttu-id="592b2-124">No caso dos componentes selecionados, digite as informações solicitadas.</span><span class="sxs-lookup"><span data-stu-id="592b2-124">For selected components, enter the requested information.</span></span> <span data-ttu-id="592b2-125">Para obter mais informações sobre caixas de diálogo individuais, consulte [referência da interface do usuário do supervisor de atualização](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span><span class="sxs-lookup"><span data-stu-id="592b2-125">For more information about individual dialog boxes, see [Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span></span>  
  
6.  <span data-ttu-id="592b2-126">Na página **confirmar a configuração do supervisor de atualização** , examine as informações inseridas.</span><span class="sxs-lookup"><span data-stu-id="592b2-126">On the **Confirm Upgrade Advisor Setting** page, review the information that you entered.</span></span> <span data-ttu-id="592b2-127">Você pode selecionar \*\*enviar relatórios para [!INCLUDE[msCoName](../../includes/msconame-md.md)] \*\* se desejar enviar seu relatório de atualização.</span><span class="sxs-lookup"><span data-stu-id="592b2-127">You can select **Send reports to [!INCLUDE[msCoName](../../includes/msconame-md.md)]** if you want to submit your upgrade report.</span></span> <span data-ttu-id="592b2-128">Você também pode visualizar a política de privacidade.</span><span class="sxs-lookup"><span data-stu-id="592b2-128">You can also review the privacy policy.</span></span>  
  
7.  <span data-ttu-id="592b2-129">Clique em **executar** para analisar a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="592b2-129">Click **Run** to analyze the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
8.  <span data-ttu-id="592b2-130">Quando a análise for concluída, clique em **Iniciar relatório** para exibir os problemas de atualização detectados.</span><span class="sxs-lookup"><span data-stu-id="592b2-130">When the analysis is finished, click **Launch Report** to view the detected upgrade issues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="592b2-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="592b2-131">See Also</span></span>  
 <span data-ttu-id="592b2-132">[Como iniciar o supervisor de atualização](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="592b2-132">[How to: Launch Upgrade Advisor](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="592b2-133">[Executando o supervisor de atualização &#40;a interface do usuário&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span><span class="sxs-lookup"><span data-stu-id="592b2-133">[Running Upgrade Advisor &#40;User Interface&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span></span>  
 [<span data-ttu-id="592b2-134">Trabalhando com o Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="592b2-134">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
