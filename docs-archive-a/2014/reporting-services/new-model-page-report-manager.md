---
title: Nova página de modelo (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 27d5bf66-b0e7-489e-a830-ffe2ec8e5350
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ed591108585b494ebb4498c1a0ab3e782693a45b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576241"
---
# <a name="new-model-page-report-manager"></a><span data-ttu-id="62da8-102">Página Novo Modelo (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="62da8-102">New Model Page (Report Manager)</span></span>
  <span data-ttu-id="62da8-103">Use essa página para gerar um modelo de relatório padrão de uma fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="62da8-103">Use this page to generate a default report model from a shared data source.</span></span> <span data-ttu-id="62da8-104">Você só pode gerar modelos de relatório de fontes de dados multidimensionais do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , Oracle e [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="62da8-104">You can only generate report models from [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] multidimensional data sources, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] relational data sources, and Oracle relational data sources.</span></span>  
  
 <span data-ttu-id="62da8-105">Modelos gerados no Gerenciador de Relatórios têm base no esquema de fonte de dados compartilhada.</span><span class="sxs-lookup"><span data-stu-id="62da8-105">Models that you generate in Report Manager are based on the schema of the shared data source.</span></span> <span data-ttu-id="62da8-106">Entidades, pastas e campos são criados para todas as tabelas e colunas na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="62da8-106">Entities, folders, and fields are created for all tables and columns in the data source.</span></span> <span data-ttu-id="62da8-107">Você não pode excluir itens nem definir opções que determinam como o modelo é gerado.</span><span class="sxs-lookup"><span data-stu-id="62da8-107">You cannot exclude items, nor can you set options that determine how the model is generated.</span></span> <span data-ttu-id="62da8-108">Para personalizar ou refinar um modelo, você deve usar o Designer de Modelo.</span><span class="sxs-lookup"><span data-stu-id="62da8-108">If you want to customize or refine a model, you must use Model Designer instead.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="62da8-109">Navegação</span><span class="sxs-lookup"><span data-stu-id="62da8-109">Navigation</span></span>  
 <span data-ttu-id="62da8-110">Use o procedimento a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="62da8-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-model-page"></a><span data-ttu-id="62da8-111">Para abrir a página Novo Modelo</span><span class="sxs-lookup"><span data-stu-id="62da8-111">To open the New Model page</span></span>  
  
1.  <span data-ttu-id="62da8-112">Abra o Gerenciador de Relatórios e localize a fonte de dados compartilhada a partir da qual você deseja gerar um modelo.</span><span class="sxs-lookup"><span data-stu-id="62da8-112">Open Report Manager, and locate the shared data source from which you want to generate a model.</span></span>  
  
2.  <span data-ttu-id="62da8-113">Focalize a fonte de dados e clique na seta para baixo.</span><span class="sxs-lookup"><span data-stu-id="62da8-113">Hover over the data source, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="62da8-114">No menu suspenso, execute uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="62da8-114">In the drop-down menu, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="62da8-115">Clique em **Gerar Modelo de Relatório** para abrir a página Novo Modelo.</span><span class="sxs-lookup"><span data-stu-id="62da8-115">Click **Generate Report Model** to open the New Model page.</span></span>  
  
    -   <span data-ttu-id="62da8-116">Clique em **Gerenciar** para abrir a página Propriedades gerais do relatório.</span><span class="sxs-lookup"><span data-stu-id="62da8-116">Click **Manage** to open the General properties page for the report.</span></span> <span data-ttu-id="62da8-117">Em seguida, clique em **Gerar Modelo** para abrir a página Novo Modelo.</span><span class="sxs-lookup"><span data-stu-id="62da8-117">Then click **Generate Model** to open the New Model page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="62da8-118">Opções</span><span class="sxs-lookup"><span data-stu-id="62da8-118">Options</span></span>  
 <span data-ttu-id="62da8-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="62da8-119">**Name**</span></span>  
 <span data-ttu-id="62da8-120">Especifica o nome do modelo.</span><span class="sxs-lookup"><span data-stu-id="62da8-120">Specifies the name of the model.</span></span> <span data-ttu-id="62da8-121">Um nome deve conter pelo menos um caractere alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="62da8-121">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="62da8-122">Também pode conter espaços e alguns símbolos.</span><span class="sxs-lookup"><span data-stu-id="62da8-122">It can also include spaces and some symbols.</span></span> <span data-ttu-id="62da8-123">Não use os seguintes caracteres ao especificar um nome:</span><span class="sxs-lookup"><span data-stu-id="62da8-123">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="62da8-124">; ?</span><span class="sxs-lookup"><span data-stu-id="62da8-124">; ?</span></span> <span data-ttu-id="62da8-125">: \@ & = +, $/\* \< > | " /</span><span class="sxs-lookup"><span data-stu-id="62da8-125">: \@ & = + , $ / \* \< > | " /</span></span>  
  
 <span data-ttu-id="62da8-126">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="62da8-126">**Description**</span></span>  
 <span data-ttu-id="62da8-127">Mostra uma descrição do modelo.</span><span class="sxs-lookup"><span data-stu-id="62da8-127">Shows a description of the model.</span></span> <span data-ttu-id="62da8-128">Os usuários que exibirem esse item no Gerenciador de Relatórios poderão ver esta descrição ao navegar na hierarquia das pastas.</span><span class="sxs-lookup"><span data-stu-id="62da8-128">Users who view this item through Report Manager see this description when browsing the folder hierarchy.</span></span>  
  
 <span data-ttu-id="62da8-129">**Alterar Local**</span><span class="sxs-lookup"><span data-stu-id="62da8-129">**Change Location**</span></span>  
 <span data-ttu-id="62da8-130">Mostra o local da pasta para o novo modelo.</span><span class="sxs-lookup"><span data-stu-id="62da8-130">Shows the folder location for the new model.</span></span> <span data-ttu-id="62da8-131">Clique no botão **Alterar Local** para selecionar outro local.</span><span class="sxs-lookup"><span data-stu-id="62da8-131">You can click the **Change Location** button to select a different location.</span></span>  
  
  
