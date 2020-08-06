---
title: Componentes SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Upgrade Advisor, components
- listing components to analyze
- Upgrade Advisor [SQL Server], components
- component analysis [Upgrade Advisor]
- finding components to analyze
- locating components to analyze
- detecting components to analyze
- server names [Upgrade Advisor]
- analyzing system [Upgrade Advisor], component list
- identifying components to analyze
ms.assetid: 539b9525-ce3f-4950-9146-5527a5a297ee
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 95fe39ce8e616b238cf7c70763e7cf1819341f16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686036"
---
# <a name="sql-server-components"></a><span data-ttu-id="b2b9b-102">Componentes do SQL Server</span><span class="sxs-lookup"><span data-stu-id="b2b9b-102">SQL Server Components</span></span>
  <span data-ttu-id="b2b9b-103">Você pode executar o assistente de análise do supervisor de atualização em um computador local ou remoto que tenha o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] , [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] ou [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] instalado.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-103">You can run the Upgrade Advisor Analysis Wizard against a local or remote computer that has [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] installed.</span></span> <span data-ttu-id="b2b9b-104">A primeira etapa da análise de pré-atualização é identificar o computador e os componentes que serão analisados.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-104">The first step in the pre-upgrade analysis is to identify the computer and components for analysis.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b2b9b-105">Opções</span><span class="sxs-lookup"><span data-stu-id="b2b9b-105">Options</span></span>  
 <span data-ttu-id="b2b9b-106">**Nome do computador**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-106">**Computer name**</span></span>  
 <span data-ttu-id="b2b9b-107">Especifica o nome do computador que será analisado.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-107">Specifies the name of the computer to analyze.</span></span> <span data-ttu-id="b2b9b-108">O supervisor de atualização popula a caixa **nome do servidor** com o nome do computador local.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-108">Upgrade Advisor populates the **Server name** box with the local computer name.</span></span> <span data-ttu-id="b2b9b-109">Também é possível usar ‘.’ e ‘localhost’ para conectar ao computador local.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-109">You can also use "." and "localhost" to connect to the local computer.</span></span>  
  
 <span data-ttu-id="b2b9b-110">Para analisar um computador diferente, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b2b9b-110">To analyze a different computer, use the following guidelines:</span></span>  
  
-   <span data-ttu-id="b2b9b-111">Para verificar instâncias não clusterizadas, insira o nome do computador.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-111">To scan nonclustered instances, enter the computer name.</span></span>  
  
-   <span data-ttu-id="b2b9b-112">Para verificar instâncias clusterizadas, digite o nome da instância do cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2b9b-112">To scan clustered instances, enter the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance.</span></span>  
  
-   <span data-ttu-id="b2b9b-113">Para verificar os componentes não clusterizados que estão instalados em um nó de um cluster, insira o nome do computador do nó de cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-113">To scan nonclustered components that are installed on a node of a cluster, enter the computer name of the failover cluster node.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b2b9b-114">Não inclua o nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2b9b-114">Do not include the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name.</span></span>  
  
 <span data-ttu-id="b2b9b-115">Em vez de especificar o nome do computador, você pode especificar o endereço IP.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-115">Instead of specifying the computer name, you can specify the IP address.</span></span>  
  
 <span data-ttu-id="b2b9b-116">Se for verificar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], você deve especificar o nome do computador local.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-116">If scanning [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must specify the name of the local computer.</span></span> <span data-ttu-id="b2b9b-117">O Supervisor de Atualização verifica somente os servidores de relatório locais.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-117">Upgrade Advisor scans local report servers only.</span></span>  
  
 <span data-ttu-id="b2b9b-118">**Detect**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-118">**Detect**</span></span>  
 <span data-ttu-id="b2b9b-119">O botão **detectar** acessa o computador especificado e detecta os componentes a serem analisados:</span><span class="sxs-lookup"><span data-stu-id="b2b9b-119">The **Detect** button accesses the specified computer and detects components to analyze:</span></span>  
  
-   <span data-ttu-id="b2b9b-120">Se você estiver analisando uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em um computador remoto, deverá habilitar os serviços de Registro remoto no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-120">If you are analyzing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance on a remote computer, you must enable the remote registry services on the remote computer.</span></span>  
  
-   <span data-ttu-id="b2b9b-121">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será detectado se uma instância do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] ou [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] for localizada no Registro do computador.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-121">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is detected if an instance of [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] is found in the computer's registry.</span></span>  
  
-   <span data-ttu-id="b2b9b-122">O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] será detectado se uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] for localizada no Registro do computador.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-122">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is detected if an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is found in the computer's registry.</span></span>  
  
-   <span data-ttu-id="b2b9b-123">O [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] é detectado se o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] for localizado no registro do computador.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-123">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is detected if [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is found in the computer's registry.</span></span> <span data-ttu-id="b2b9b-124">Entretanto, o Supervisor de Atualização verifica somente os servidores de relatório locais.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-124">However, Upgrade Advisor scans local report servers only.</span></span>  
  
 <span data-ttu-id="b2b9b-125">**Componentes**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-125">**Components**</span></span>  
 <span data-ttu-id="b2b9b-126">Selecione os componentes que serão analisados.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-126">Select the components to analyze.</span></span> <span data-ttu-id="b2b9b-127">Você pode clicar no botão **detectar** para selecionar todos os componentes instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-127">You can click the **Detect** button to select all the components installed on the computer.</span></span> <span data-ttu-id="b2b9b-128">Uma marca de seleção aparecerá próximo aos componentes que forem detectados como instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-128">A check mark will appear next to the components that are detected as installed on the computer.</span></span> <span data-ttu-id="b2b9b-129">Você também pode selecionar manualmente os componentes que serão analisados. Basta selecionar ou desmarcar a caixa próxima a cada componente.</span><span class="sxs-lookup"><span data-stu-id="b2b9b-129">You can also manually select the components to analyze by selecting or clearing the check box next to each component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b9b-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b2b9b-130">See Also</span></span>  
 <span data-ttu-id="b2b9b-131">[Trabalhando com o supervisor de atualização](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="b2b9b-131">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="b2b9b-132">Referência da interface de usuário do Supervisor de Atualização</span><span class="sxs-lookup"><span data-stu-id="b2b9b-132">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
