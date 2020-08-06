---
title: Caixa de diálogo Habilitar-Desabilitar Write-back (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitiondesigner.writebackenabledisable.f1
ms.assetid: 2d254393-3f0d-4b70-8b98-87159f9f3639
author: minewiskan
ms.author: owend
ms.openlocfilehash: 54ee4597ee78f45682730bd0e8d7119d204eaf2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583874"
---
# <a name="enable-disable-writeback-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="58e7a-102">Caixa de diálogo Habilitar-Desabilitar Write-back (Analysis Services-dados multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="58e7a-102">Enable-Disable Writeback Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="58e7a-103">A caixa de diálogo **Habilitar/Desabilitar Write-back** habilita ou desabilita write-back para um grupo de medidas em um cubo.</span><span class="sxs-lookup"><span data-stu-id="58e7a-103">The **Enable/Disable Writeback** dialog box enables or disables writeback for a measure group in a cube.</span></span> <span data-ttu-id="58e7a-104">Habilitar write-back em um grupo de medidas define uma partição de write-back e cria uma tabela de write-back para esse grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="58e7a-104">Enabling writeback on a measure group defines a writeback partition and creates a writeback table for that measure group.</span></span> <span data-ttu-id="58e7a-105">Desabilitar write-back em um grupo de medidas remove a partição de write-back, mas não exclui a tabela de write-back, de modo a evitar perda de dados inesperada.</span><span class="sxs-lookup"><span data-stu-id="58e7a-105">Disabling writeback on a measure group removes the writeback partition but does not delete the writeback table, to avoid unanticipated data loss.</span></span> <span data-ttu-id="58e7a-106">A caixa de diálogo **Habilitar/Desabilitar Write-back** é exibida da seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="58e7a-106">The **Enable/Disable Writeback** dialog box is displayed by:</span></span>  
  
-   <span data-ttu-id="58e7a-107">Clicando em **Configurações de Write-back** no painel **Grupos de Medidas** na guia **Partições** no Designer de Cubo.</span><span class="sxs-lookup"><span data-stu-id="58e7a-107">Clicking **Writeback Settings** in the **Measure Groups** pane on the **Partitions** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="58e7a-108">Clicando com o botão direito do mouse na grade **Partições** no painel **Grupos de Medidas** na guia **Partições** no Designer de Cubo e selecionando **Configurações de Write-back** no menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="58e7a-108">Right-clicking a partition in the **Partitions** grid in the **Measure Groups** pane on the **Partitions** tab in Cube Designer and selecting **Writeback Settings** from the context menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="58e7a-109">Opções</span><span class="sxs-lookup"><span data-stu-id="58e7a-109">Options</span></span>  
 <span data-ttu-id="58e7a-110">**Nome da tabela**</span><span class="sxs-lookup"><span data-stu-id="58e7a-110">**Table name**</span></span>  
 <span data-ttu-id="58e7a-111">Digite o nome da tabela de write-back a ser criada para a partição selecionada.</span><span class="sxs-lookup"><span data-stu-id="58e7a-111">Type the name of the writeback table to create for the selected partition.</span></span> <span data-ttu-id="58e7a-112">A tabela write-back armazena as alterações feitas no grupo de medidas por um aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="58e7a-112">The writeback table stores the changes made to the measure group from a client application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="58e7a-113">Essa opção estará desabilitada se write-back não estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="58e7a-113">This option is disabled if writeback is not enabled.</span></span>  
  
 <span data-ttu-id="58e7a-114">**Fonte de dados**</span><span class="sxs-lookup"><span data-stu-id="58e7a-114">**Data source**</span></span>  
 <span data-ttu-id="58e7a-115">Selecione a fonte de dados para conter a tabela de write-back.</span><span class="sxs-lookup"><span data-stu-id="58e7a-115">Select the data source to contain the writeback table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="58e7a-116">Essa opção estará desabilitada se write-back não estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="58e7a-116">This option is disabled if writeback is not enabled.</span></span>  
  
 <span data-ttu-id="58e7a-117">**Novo**</span><span class="sxs-lookup"><span data-stu-id="58e7a-117">**New**</span></span>  
 <span data-ttu-id="58e7a-118">Clique para exibir a caixa de diálogo **Gerenciador de Conexões** e definir uma nova fonte de dados para conter a tabela de write-back.</span><span class="sxs-lookup"><span data-stu-id="58e7a-118">Click to display the **Connection Manager** dialog box and define a new data source to contain the writeback table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="58e7a-119">Essa opção estará desabilitada se write-back não estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="58e7a-119">This option is disabled if writeback is not enabled.</span></span>  
  
  
