---
title: Microsoft Connector 1,1 para SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5281f080-53d5-4679-aa26-f4cd4ac7a2df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ec5cfe83b201976be0512c54b77bc79f8aa824b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683601"
---
# <a name="microsoft-connector-11-for-sap-bw"></a><span data-ttu-id="d5b89-102">Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="d5b89-102">Microsoft Connector 1.1 for SAP BW</span></span>
  <span data-ttu-id="d5b89-103">O [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW consiste em um conjunto de três componentes que permite a você extrair dados do sistema SAP Netweaver BW versão 7 ou carregar dados nele.</span><span class="sxs-lookup"><span data-stu-id="d5b89-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW consists of a set of three components that let you extract data from, or load data into, an SAP Netweaver BW version 7 system.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d5b89-104">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d5b89-104">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="d5b89-105">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="d5b89-105">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d5b89-106">A extração de dados do SAP Netweaver BW exige licenciamento SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="d5b89-106">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="d5b89-107">Verifique esses requisitos com a SAP.</span><span class="sxs-lookup"><span data-stu-id="d5b89-107">Check with SAP to verify these requirements.</span></span>  
  
## <a name="components"></a><span data-ttu-id="d5b89-108">Componentes</span><span class="sxs-lookup"><span data-stu-id="d5b89-108">Components</span></span>  
 <span data-ttu-id="d5b89-109">O [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW tem os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="d5b89-109">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW has the following components:</span></span>  
  
-   <span data-ttu-id="d5b89-110">**Fonte de SAP BW**-a fonte de SAP BW é um componente de fonte de fluxo de dados que permite extrair dados de um sistema SAP NetWeaver BW versão 7.</span><span class="sxs-lookup"><span data-stu-id="d5b89-110">**SAP BW Source**-The SAP BW source is a data flow source component that lets you extract data from an SAP Netweaver BW version 7 system.</span></span>  
  
-   <span data-ttu-id="d5b89-111">**Destino de SAP BW**-o destino de SAP BW é um componente de destino de fluxo de dados que permite carregar dados em um sistema SAP NetWeaver BW versão 7.</span><span class="sxs-lookup"><span data-stu-id="d5b89-111">**SAP BW Destination**-The SAP BW destination is a data flow destination component that lets you load data into an SAP Netweaver BW version 7 system.</span></span>  
  
-   <span data-ttu-id="d5b89-112">**SAP BW Gerenciador de conexões**– o SAP BW Gerenciador de conexões conecta uma fonte SAP BW ou destino de SAP BW a um sistema SAP NetWeaver BW versão 7.</span><span class="sxs-lookup"><span data-stu-id="d5b89-112">**SAP BW Connection Manager**-The SAP BW connection manager connects either an SAP BW source or SAP BW destination to an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="d5b89-113">Para obter um passo a passo que demonstre como configurar e usar o gerenciador de conexões do SAP BW, a origem e o destino, consulte o white paper [Usando o SQL Server Integration Services com SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkId=301897).</span><span class="sxs-lookup"><span data-stu-id="d5b89-113">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkId=301897).</span></span> <span data-ttu-id="d5b89-114">Este white paper também mostra como configurar os objetos necessários no SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d5b89-114">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
## <a name="documentation"></a><span data-ttu-id="d5b89-115">Documentação</span><span class="sxs-lookup"><span data-stu-id="d5b89-115">Documentation</span></span>  
 <span data-ttu-id="d5b89-116">Este arquivo da Ajuda para o [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW contém os seguintes tópicos e seções:</span><span class="sxs-lookup"><span data-stu-id="d5b89-116">This Help file for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW contains the following topics and sections:</span></span>  
  
 [<span data-ttu-id="d5b89-117">Instalando o Microsoft Connector para 1.1 SAP BW</span><span class="sxs-lookup"><span data-stu-id="d5b89-117">Installing the Microsoft Connector for 1.1 SAP BW</span></span>](installing-the-microsoft-connector-for-sap-bw.md)  
 <span data-ttu-id="d5b89-118">Descreve os requisitos de instalação para o [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d5b89-118">Describes the installation requirements for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 [<span data-ttu-id="d5b89-119">Componentes do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="d5b89-119">Microsoft Connector 1.1 for SAP BW Components</span></span>](microsoft-connector-for-sap-bw-components.md)  
 <span data-ttu-id="d5b89-120">Descreve cada componente do [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d5b89-120">Describes each component of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 [<span data-ttu-id="d5b89-121">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="d5b89-121">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](microsoft-connector-for-sap-bw-f1-help.md)  
 <span data-ttu-id="d5b89-122">Descreve a interface do usuário de cada componente do [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d5b89-122">Describes the user interface of each component of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
  
