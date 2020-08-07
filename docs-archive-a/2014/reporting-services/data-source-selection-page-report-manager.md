---
title: Página seleção de fonte de dados (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7f7e8b19-0c0b-4b1f-9cc1-057099aa07eb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 03c5558397786b02b764b78d47584d9b190290cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575639"
---
# <a name="data-source-selection-page-report-manager"></a><span data-ttu-id="c0ebd-102">Página Seleção de Fonte de Dados (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="c0ebd-102">Data Source Selection Page (Report Manager)</span></span>
  <span data-ttu-id="c0ebd-103">Use a página Seleção de Fonte de Dados para selecionar um item de fonte de dados compartilhada existente a ser usado em um relatório ou modelo de relatório.</span><span class="sxs-lookup"><span data-stu-id="c0ebd-103">Use the Data Source Selection page to select an existing shared data source item to use with a report or a report model.</span></span> <span data-ttu-id="c0ebd-104">Você também pode usar essa página para selecionar uma fonte de dados diferente.</span><span class="sxs-lookup"><span data-stu-id="c0ebd-104">You can also use this page to select a different data source.</span></span> <span data-ttu-id="c0ebd-105">Para exibir o tipo de fonte de dados ou a cadeia de conexão, é necessário navegar até a fonte de dados compartilhada e abrir a página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="c0ebd-105">To view the data source type or connection string, you must navigate to the shared data source and open the property pages.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="c0ebd-106">Navegação</span><span class="sxs-lookup"><span data-stu-id="c0ebd-106">Navigation</span></span>  
 <span data-ttu-id="c0ebd-107">Use o procedimento a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="c0ebd-107">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-data-source-selection-page"></a><span data-ttu-id="c0ebd-108">Para abrir a página Seleção de Fonte de Dados</span><span class="sxs-lookup"><span data-stu-id="c0ebd-108">To open the Data Source Selection page</span></span>  
  
1.  <span data-ttu-id="c0ebd-109">Abra o Gerenciador de Relatórios e localize o relatório ou modelo para o qual você deseja selecionar uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c0ebd-109">Open Report Manager, and locate the report or model for which you want to select a data source.</span></span>  
  
2.  <span data-ttu-id="c0ebd-110">Focalize o relatório e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="c0ebd-110">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="c0ebd-111">No menu suspenso, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="c0ebd-111">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="c0ebd-112">Esse procedimento abre a página Propriedades gerais do modelo.</span><span class="sxs-lookup"><span data-stu-id="c0ebd-112">This opens the General properties page for the report or model.</span></span>  
  
4.  <span data-ttu-id="c0ebd-113">Selecione a guia **Fontes de Dados** .</span><span class="sxs-lookup"><span data-stu-id="c0ebd-113">Select the **Data Sources** tab.</span></span>  
  
5.  <span data-ttu-id="c0ebd-114">No painel de propriedades, selecione **Uma fonte de dados compartilhados** e clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="c0ebd-114">In the properties pane, select **A shared data source** and then click **Browse**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c0ebd-115">Opções</span><span class="sxs-lookup"><span data-stu-id="c0ebd-115">Options</span></span>  
 <span data-ttu-id="c0ebd-116">**Localidade**</span><span class="sxs-lookup"><span data-stu-id="c0ebd-116">**Location**</span></span>  
 <span data-ttu-id="c0ebd-117">Especifique o caminho completo para o item de fonte de dados compartilhada, começando pelo nome da pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="c0ebd-117">Specify the full path to the shared data source item, beginning with the root folder name.</span></span> <span data-ttu-id="c0ebd-118">É possível digitar o caminho completo da pasta ou usar a exibição de árvore para navegar até a fonte de dados compartilhada desejada.</span><span class="sxs-lookup"><span data-stu-id="c0ebd-118">You can type the path name or use the tree view to navigate to the shared data source you want.</span></span>  
  
 <span data-ttu-id="c0ebd-119">**Modo de exibição de árvore**</span><span class="sxs-lookup"><span data-stu-id="c0ebd-119">**Tree view**</span></span>  
 <span data-ttu-id="c0ebd-120">Mostra a estrutura de pasta do namespace do servidor de relatórios.</span><span class="sxs-lookup"><span data-stu-id="c0ebd-120">Shows the folder structure of the report server namespace.</span></span> <span data-ttu-id="c0ebd-121">Clique em um item de fonte de dados compartilhada para adicionar o caminho completo até o campo **Local** .</span><span class="sxs-lookup"><span data-stu-id="c0ebd-121">Click a shared data source item to add the full path to the **Location** field.</span></span>  
  
 <span data-ttu-id="c0ebd-122">**OK**</span><span class="sxs-lookup"><span data-stu-id="c0ebd-122">**OK**</span></span>  
 <span data-ttu-id="c0ebd-123">Clique para copiar a seleção de fonte de dados para a página de propriedades Fontes de Dados.</span><span class="sxs-lookup"><span data-stu-id="c0ebd-123">Click to copy the data source selection to the Data Sources properties page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ebd-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c0ebd-124">See Also</span></span>  
 <span data-ttu-id="c0ebd-125">[Gerenciar fontes de dados de relatório](report-data/manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="c0ebd-125">[Manage Report Data Sources](report-data/manage-report-data-sources.md) </span></span>  
 <span data-ttu-id="c0ebd-126">[Especificar informações de credenciais e de conexão para fontes de dados de relatório](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="c0ebd-126">[Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span></span>  
 <span data-ttu-id="c0ebd-127">[Página Propriedades das fontes de dados &#40;Report Manager&#41;](../../2014/reporting-services/data-sources-properties-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c0ebd-127">[Data Sources Properties Page &#40;Report Manager&#41;](../../2014/reporting-services/data-sources-properties-page-report-manager.md) </span></span>  
 <span data-ttu-id="c0ebd-128">[Nova página de fonte de dados &#40;Report Manager&#41;](../../2014/reporting-services/new-data-source-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c0ebd-128">[New Data Source Page &#40;Report Manager&#41;](../../2014/reporting-services/new-data-source-page-report-manager.md) </span></span>  
 [<span data-ttu-id="c0ebd-129">Ajuda F1 do Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="c0ebd-129">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
