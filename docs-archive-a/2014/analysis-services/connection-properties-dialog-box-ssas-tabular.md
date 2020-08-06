---
title: Caixa de diálogo Propriedades da conexão (SSAS-tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.ssmsimbi.ConnectionProperties.F1
ms.assetid: 17bae8ae-2ba0-4978-be70-61c687f59d54
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e4b0360d59f43bc932f68a846f239c4873a5aa9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571000"
---
# <a name="connection-properties-dialog-box-ssas---tabular"></a><span data-ttu-id="e4f21-102">Caixa de diálogo Propriedades da Conexão (SSAS – Tabular)</span><span class="sxs-lookup"><span data-stu-id="e4f21-102">Connection Properties Dialog Box (SSAS - Tabular)</span></span>
  <span data-ttu-id="e4f21-103">Use esta página para exibir ou modificar no SQL Server Management Studio as propriedades de conexão de uma fonte de dados usada por um banco de dados modelo de tabela.</span><span class="sxs-lookup"><span data-stu-id="e4f21-103">Use this page to view or modify in SQL Server Management Studio the connection properties of a data source used by a tabular model database.</span></span>  
  
 <span data-ttu-id="e4f21-104">Esta caixa de diálogo fornece carimbos de data/hora e outras informações descritivas, mais propriedades personalizáveis que determinam as características da conexão.</span><span class="sxs-lookup"><span data-stu-id="e4f21-104">This dialog box provides timestamps and other descriptive information, plus customizable properties that determine characteristics of the connection.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e4f21-105">Opções</span><span class="sxs-lookup"><span data-stu-id="e4f21-105">Options</span></span>  
  
|<span data-ttu-id="e4f21-106">Termo</span><span class="sxs-lookup"><span data-stu-id="e4f21-106">Term</span></span>|<span data-ttu-id="e4f21-107">Definição</span><span class="sxs-lookup"><span data-stu-id="e4f21-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="e4f21-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e4f21-108">**Name**</span></span>|<span data-ttu-id="e4f21-109">Especifica o nome da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e4f21-109">Specifies the name of the data source.</span></span>|  
|<span data-ttu-id="e4f21-110">**ID**</span><span class="sxs-lookup"><span data-stu-id="e4f21-110">**ID**</span></span>|<span data-ttu-id="e4f21-111">Exibe o identificador do objeto de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e4f21-111">Displays the identifier of the data source object.</span></span>|  
|<span data-ttu-id="e4f21-112">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e4f21-112">**Description**</span></span>|<span data-ttu-id="e4f21-113">Exibe a descrição do objeto de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="e4f21-113">Displays the description of the data source object.</span></span>|  
|<span data-ttu-id="e4f21-114">**Criar Carimbo de Data/Hora**</span><span class="sxs-lookup"><span data-stu-id="e4f21-114">**Create Timestamp**</span></span>|<span data-ttu-id="e4f21-115">Exibe a data e a hora de criação do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e4f21-115">Displays the date and time the database was created.</span></span>|  
|<span data-ttu-id="e4f21-116">**Última Atualização de Esquema**</span><span class="sxs-lookup"><span data-stu-id="e4f21-116">**Last Schema Update**</span></span>|<span data-ttu-id="e4f21-117">Exibe a data e a hora da última atualização dos metadados do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e4f21-117">Displays the date and time the metadata for the database was last updated.</span></span>|  
|<span data-ttu-id="e4f21-118">**Cadeia de conexão**</span><span class="sxs-lookup"><span data-stu-id="e4f21-118">**Connection String**</span></span>|<span data-ttu-id="e4f21-119">Exibe a cadeia de conexão que é usada para conectar-se à fonte de dados que fornece dados ao modelo.</span><span class="sxs-lookup"><span data-stu-id="e4f21-119">Displays the connection string used to connect to the data source that provides data to the model.</span></span>|  
|<span data-ttu-id="e4f21-120">**Número máximo de conexões**</span><span class="sxs-lookup"><span data-stu-id="e4f21-120">**Maximum Number of Connections**</span></span>|<span data-ttu-id="e4f21-121">Especifica o número máximo de conexões cliente com esse banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e4f21-121">Specifies the maximum number of client connections to this database.</span></span>|  
|<span data-ttu-id="e4f21-122">**Isolamento**</span><span class="sxs-lookup"><span data-stu-id="e4f21-122">**Isolation**</span></span>|<span data-ttu-id="e4f21-123">Os valores válidos são ReadCommitted ou Snapshot.</span><span class="sxs-lookup"><span data-stu-id="e4f21-123">Valid values are ReadCommitted or Snapshot.</span></span> <span data-ttu-id="e4f21-124">Para obter mais informações, consulte [Elemento Isolation &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/isolation-element-assl).</span><span class="sxs-lookup"><span data-stu-id="e4f21-124">For more information, see [Isolation Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/isolation-element-assl).</span></span>|  
|<span data-ttu-id="e4f21-125">**Tempo Limite da Consulta**</span><span class="sxs-lookup"><span data-stu-id="e4f21-125">**Query Timeout**</span></span>|<span data-ttu-id="e4f21-126">Especifica a hora, em segundos, depois da qual a tentativa de recuperar dados se esgota.</span><span class="sxs-lookup"><span data-stu-id="e4f21-126">Specifies the time, in seconds, after which an attempt to retrieve data is timed out.</span></span>|  
|<span data-ttu-id="e4f21-127">**Provedor Gerenciado**</span><span class="sxs-lookup"><span data-stu-id="e4f21-127">**Managed Provider**</span></span>|<span data-ttu-id="e4f21-128">Especifica o nome do provedor gerenciado.</span><span class="sxs-lookup"><span data-stu-id="e4f21-128">Specifies the name of the managed provider.</span></span> <span data-ttu-id="e4f21-129">Se a conexão da fonte de dados usar um provedor OLE DB nativo, esse valor será vazio.</span><span class="sxs-lookup"><span data-stu-id="e4f21-129">If the data source connection uses a native OLE DB provider, this value is empty.</span></span>|  
|<span data-ttu-id="e4f21-130">**Informações sobre Representação**</span><span class="sxs-lookup"><span data-stu-id="e4f21-130">**Impersonation Info**</span></span>|<span data-ttu-id="e4f21-131">Especifica a conta de representação usada para conexões de banco de dados durante o processamento ou a atualização de dados, consultas executadas em um repositório de dados relacional (via DirectQuery), associações fora de linha, partições remotas e sincronização de banco de dados do destino para a origem.</span><span class="sxs-lookup"><span data-stu-id="e4f21-131">Specifies the impersonation account used for database connections when processing or refreshing data, queries that run against a relational data store (via DirectQuery), out-of-line bindings, remote partitions, and database synchronization from target to source.</span></span><br /><br /> <span data-ttu-id="e4f21-132">Os valores válidos incluem a conta de serviço do Analysis Services ou um conjunto específico de credenciais do Windows.</span><span class="sxs-lookup"><span data-stu-id="e4f21-132">Valid values include the Analysis Services service account or a specific set of Windows credentials.</span></span> <span data-ttu-id="e4f21-133">Não especifique **Usar as credenciais do usuário atual** ou **Herdar**.</span><span class="sxs-lookup"><span data-stu-id="e4f21-133">Do not specify **Use the credentials of the current user** or **Inherit**.</span></span> <span data-ttu-id="e4f21-134">Não há suporte para essas opções de credencial para um banco de dados modelo de tabela.</span><span class="sxs-lookup"><span data-stu-id="e4f21-134">Those credential options are not supported for a tabular model database.</span></span>|  
  
  
