---
title: Configurar propriedades de um coletor de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.datacollectionprop.advanced.f1
- sql12.swb.dc.datacollectionprop.general.f1
ms.assetid: cf98f57d-5a6d-4bc3-bf10-783e460fc63d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 05172c2c831ec649269512a625be069cdc67047a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681687"
---
# <a name="configure-properties-of-a-data-collector"></a><span data-ttu-id="a94de-102">Configurar propriedades de um coletor de dados</span><span class="sxs-lookup"><span data-stu-id="a94de-102">Configure Properties of a Data Collector</span></span>
  <span data-ttu-id="a94de-103">Este tópico discute como você pode configurar as propriedades de um coletor de dados.</span><span class="sxs-lookup"><span data-stu-id="a94de-103">This topic discusses how you can configure the properties of a data collector.</span></span>  
  
## <a name="data-collection-properties-general-tab"></a><span data-ttu-id="a94de-104">Propriedades de Coleta de Dados (guia Geral)</span><span class="sxs-lookup"><span data-stu-id="a94de-104">Data Collection Properties (General Tab)</span></span>  
 <span data-ttu-id="a94de-105">Use esta página para definir configurações para o data warehouse de gerenciamento e especifique em que lugar os dados coletados devem ser armazenados antes de serem carregados no data warehouse.</span><span class="sxs-lookup"><span data-stu-id="a94de-105">Use this page to configure settings for the management data warehouse and specify where collected data should be stored before it is uploaded to the data warehouse.</span></span>  
  
 <span data-ttu-id="a94de-106">**Habilitar Coleta de Dados**</span><span class="sxs-lookup"><span data-stu-id="a94de-106">**Enable Data Collection**</span></span>  
 <span data-ttu-id="a94de-107">Selecione para habilitar a coleta de dados.</span><span class="sxs-lookup"><span data-stu-id="a94de-107">Select to enable data collection.</span></span> <span data-ttu-id="a94de-108">Essa opção tem o mesmo efeito da execução do procedimento armazenado sp_syscollector_enable_collector.</span><span class="sxs-lookup"><span data-stu-id="a94de-108">This has the same effect as running the sp_syscollector_enable_collector stored procedure.</span></span> <span data-ttu-id="a94de-109">Desmarcar essa caixa de seleção desabilita a coleta de dados e tem o mesmo efeito da execução do procedimento armazenado sp_syscollector_disable_collector.</span><span class="sxs-lookup"><span data-stu-id="a94de-109">Clearing this check box disables data collection and has the same effect as running the sp_syscollector_disable_collector stored procedure.</span></span>  
  
 <span data-ttu-id="a94de-110">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="a94de-110">**Server**</span></span>  
 <span data-ttu-id="a94de-111">Exibe o nome do servidor que hospedará o data warehouse de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="a94de-111">Displays the name of the server that will host the management data warehouse</span></span>  
  
 <span data-ttu-id="a94de-112">**Nome do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="a94de-112">**Database name**</span></span>  
 <span data-ttu-id="a94de-113">Exibe o nome do banco de dados relacional que é usado para o data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="a94de-113">Displays the name of the relational database that is used for the management data warehouse.</span></span>  
  
 <span data-ttu-id="a94de-114">**Testar Conexão**</span><span class="sxs-lookup"><span data-stu-id="a94de-114">**Test Connection**</span></span>  
 <span data-ttu-id="a94de-115">Teste a conexão ao **Servidor** especificado usando as informações fornecidas quando a coleta de dados foi configurada.</span><span class="sxs-lookup"><span data-stu-id="a94de-115">Test the connection to the specified **Server** using information provided when data collection is configured.</span></span>  
  
 <span data-ttu-id="a94de-116">**Diretório de cache**</span><span class="sxs-lookup"><span data-stu-id="a94de-116">**Cache directory**</span></span>  
 <span data-ttu-id="a94de-117">Especifica o diretório em que os dados coletados são armazenados no sistema que coleta os dados antes de eles serem carregados no data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="a94de-117">Specifies the directory where collected data is stored on the system collecting the data before it is uploaded to the management data warehouse.</span></span> <span data-ttu-id="a94de-118">Se o **Diretório de cache** não for especificado, o coletor de dados tentará localizar o %TEMP% e as variáveis de ambiente %TMP% e usará um desses locais como local padrão para armazenamento temporário.</span><span class="sxs-lookup"><span data-stu-id="a94de-118">If **Cache directory** is not specified, the data collector attempts to locate the %TEMP% and %TMP% environment variables and use one these locations as the default location for temporary storage.</span></span> <span data-ttu-id="a94de-119">Se essas variáveis de ambiente não forem configuradas, ocorrerá um e você será solicitado a criar um diretório de cache.</span><span class="sxs-lookup"><span data-stu-id="a94de-119">If these environment variables are not configured, an error occurs and you are prompted to create a cache directory.</span></span>  
  
## <a name="data-collection-properties-advanced-tab"></a><span data-ttu-id="a94de-120">Propriedades de Coleta de Dados (guia Avançado)</span><span class="sxs-lookup"><span data-stu-id="a94de-120">Data Collection Properties (Advanced Tab)</span></span>  
 <span data-ttu-id="a94de-121">Use esta página para configurar os parâmetros de tentativa da conexão ao data warehouse de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="a94de-121">Use this page to configure the retry settings for the connection to the management data warehouse.</span></span>  
  
 <span data-ttu-id="a94de-122">**Número de tentativas se o carregamento falhar**</span><span class="sxs-lookup"><span data-stu-id="a94de-122">**Number of times to retry if upload fails**</span></span>  
 <span data-ttu-id="a94de-123">Especifica o número de novas tentativas de carregamento no data warehouse de gerenciamento se o carregamento falhar.</span><span class="sxs-lookup"><span data-stu-id="a94de-123">Specifies the number of times to retry an upload to the management data warehouse if an upload fails.</span></span> <span data-ttu-id="a94de-124">O padrão é 1.</span><span class="sxs-lookup"><span data-stu-id="a94de-124">The default is 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a94de-125">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a94de-125">See Also</span></span>  
 <span data-ttu-id="a94de-126">[Gerenciar coleta de dados](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="a94de-126">[Manage Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="a94de-127">Configurar o Data Warehouse de Gerenciamento &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a94de-127">Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;</span></span>](configure-the-management-data-warehouse-sql-server-management-studio.md)  
  
  
