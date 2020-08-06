---
title: Conectar-se a uma fonte de dados (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.conndatasource.f1
ms.assetid: 1e2b17e9-092b-4af1-8a58-c52b8fe10ff1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4fe7f7d5b31118369b8ce2a855b955e44f661dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571032"
---
# <a name="connect-to-a-data-source-ssas"></a><span data-ttu-id="6951b-102">Conectar com uma fonte de dados (SSAS)</span><span class="sxs-lookup"><span data-stu-id="6951b-102">Connect to a Data Source (SSAS)</span></span>
  <span data-ttu-id="6951b-103">Esta página do **Assistente de Importação de Tabela** o habilita a criar uma nova conexão com várias fontes de dados, como bancos de dados relacionais, feeds de dados e arquivos.</span><span class="sxs-lookup"><span data-stu-id="6951b-103">This page of the **Table Import Wizard** enables you to create a new data source connection to a variety of data sources, such as relational databases, data feeds, and files.</span></span> <span data-ttu-id="6951b-104">Para acessar o assistente do [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], no menu **Modelo** , clique em **Importar de Fonte de Dados**.</span><span class="sxs-lookup"><span data-stu-id="6951b-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="6951b-105">Para conectar uma fonte de dados, você deve ter o provedor apropriado instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="6951b-105">To connect to a data source, you must have the appropriate provider installed on your machine.</span></span> <span data-ttu-id="6951b-106">Você também deve ter o provedor apropriado instalado no servidor de banco de dados de workspace.</span><span class="sxs-lookup"><span data-stu-id="6951b-106">You must also have the appropriate provider installed on the workspace database server.</span></span> <span data-ttu-id="6951b-107">Para servidores de 32 bits (x86), provedores de 32 bits devem ser instalados.</span><span class="sxs-lookup"><span data-stu-id="6951b-107">For 32-bit (x86) servers, 32-bit providers must be installed.</span></span> <span data-ttu-id="6951b-108">Para servidores de 64 bits (x64), provedores de 64 bits devem ser instalados.</span><span class="sxs-lookup"><span data-stu-id="6951b-108">For 64-bit (x64) servers, 64-bit providers must be installed.</span></span>  
  
 [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] <span data-ttu-id="6951b-109">é sempre executado em um processo de 32 bits, independentemente da arquitetura.</span><span class="sxs-lookup"><span data-stu-id="6951b-109">always runs in a 32-bit process, regardless of architecture.</span></span> <span data-ttu-id="6951b-110">Ao executar [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] em um computador de 64 bits, você deve estar consciente do seguinte ao instalar provedores de dados:</span><span class="sxs-lookup"><span data-stu-id="6951b-110">When running [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] on a 64-bit machine, you should be aware of the following when installing data providers:</span></span>  
  
-   <span data-ttu-id="6951b-111">Para provedores que dão suporte à instalação lado a lado de provedores de 32 bits e de 64 bits, você deve instalar ambos os provedores.</span><span class="sxs-lookup"><span data-stu-id="6951b-111">For providers that support side-by-side installation of 32-bit and 64-bit providers, you should install both providers.</span></span>  
  
-   <span data-ttu-id="6951b-112">Para o provedor ACE, você deve instalar a versão de 64 bits do provedor.</span><span class="sxs-lookup"><span data-stu-id="6951b-112">For the ACE provider, you must install the 64-bit version of the provider.</span></span> <span data-ttu-id="6951b-113">Como o Office instala o provedor de ACE automaticamente, você não deve executar uma versão de 32 bits do Microsoft Office em um computador de 64 bits que hospeda o servidor de banco de dados de workspace.</span><span class="sxs-lookup"><span data-stu-id="6951b-113">Because Office automatically installs the ACE provider, you should not run a 32-bit version of Microsoft Office on a 64-bit machine hosting the workspace database server.</span></span>  
  
     <span data-ttu-id="6951b-114">O provedor ACE é usado para importar de arquivos de Texto, do Excel e do Access.</span><span class="sxs-lookup"><span data-stu-id="6951b-114">The ACE provider is used to import from Text, Excel, and Access files.</span></span> <span data-ttu-id="6951b-115">Se o suporte a essas fontes de dados não for necessário, você poderá executar uma versão de 32 bits do Microsoft Office em um computador que executa um servidor de banco de dados de workspace de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="6951b-115">If support for these data sources is not needed, you can then run a 32-bit version of Microsoft Office on a machine running a 64-bit workspace database server.</span></span>  
  
-   <span data-ttu-id="6951b-116">Para outros provedores que não dão suporte à instalação lado a lado de provedores de 32 bits e de 64 bits, instale o provedor de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="6951b-116">For other providers that do not support side-by-side installation of 32-bit and 64-bit providers, you must install the 32-bit provider.</span></span> <span data-ttu-id="6951b-117">Se apenas computadores de 64 bits estiverem disponíveis, use um computador remoto com um provedor de 64 bits instalado como o servidor de banco de dados de workspace.</span><span class="sxs-lookup"><span data-stu-id="6951b-117">If only 64-bit machines are available, you must use a remote machine with a 64-bit provider installed as the workspace database server.</span></span>  
  
  
