---
title: Configurar propriedades gerais para um relatório (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], properties
- properties [Reporting Services], general
ms.assetid: 10b941b2-28e6-4408-9ee4-acebc63c8496
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f30900158591afcd5997053dbb61cc22b495ed10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684605"
---
# <a name="configure-general-properties-for-a-report-report-manager"></a><span data-ttu-id="d8fed-102">Configurar as propriedades gerais de um relatório (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="d8fed-102">Configure General Properties for a Report (Report Manager)</span></span>
  
### <a name="to-configure-general-report-properties"></a><span data-ttu-id="d8fed-103">Para configurar as propriedades gerais do relatório</span><span class="sxs-lookup"><span data-stu-id="d8fed-103">To configure general report properties</span></span>

1.  <span data-ttu-id="d8fed-104">Inicie o [Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="d8fed-104">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span></span>

2.  <span data-ttu-id="d8fed-105">Em Report Manager, navegue até a página **conteúdo** .</span><span class="sxs-lookup"><span data-stu-id="d8fed-105">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="d8fed-106">Navegue até o relatório para o qual deseja configurar as propriedades gerais e abra-o.</span><span class="sxs-lookup"><span data-stu-id="d8fed-106">Navigate to the report that you want to configure general properties for and open it.</span></span>

3.  <span data-ttu-id="d8fed-107">Clique no guia **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d8fed-107">Click the **Properties** tab.</span></span>

     <span data-ttu-id="d8fed-108">Ou, se a página **conteúdo** estiver no modo de exibição de detalhes, clique no ícone da página de propriedades:</span><span class="sxs-lookup"><span data-stu-id="d8fed-108">Or, if the **Contents** page is in Details view, click the property page icon:</span></span>

     <span data-ttu-id="d8fed-109">![Ícone da página de propriedades](media/prop.gif "Ícone da página de propriedades")</span><span class="sxs-lookup"><span data-stu-id="d8fed-109">![Property page icon](media/prop.gif "Property page icon")</span></span>

4.  <span data-ttu-id="d8fed-110">A página Propriedades **gerais** é exibida e você pode configurar as propriedades da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d8fed-110">The **General** properties page is displayed, and you can configure properties as follows:</span></span>

    -   <span data-ttu-id="d8fed-111">Na seção **Propriedades** , você pode modificar o nome e a descrição do relatório.</span><span class="sxs-lookup"><span data-stu-id="d8fed-111">In the **Properties** section, you can modify the report name and description.</span></span>

    -   <span data-ttu-id="d8fed-112">Você pode marcar a caixa de seleção **ocultar na exibição de lista** para ocultar o item quando a página for aberta no layout de página padrão (modo de exibição de lista) que organiza os itens na página.</span><span class="sxs-lookup"><span data-stu-id="d8fed-112">You can select the **Hide in list view** checkbox to hide the item when the page is opened in the default page layout (list view) which arranges items across and down the page.</span></span>

    -   <span data-ttu-id="d8fed-113">Na seção **definição de relatório** , clique em **Editar** para extrair uma cópia da definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="d8fed-113">In the **Report Definition** section, click **Edit** to extract a copy of the report definition.</span></span> <span data-ttu-id="d8fed-114">As modificações feitas localmente na definição de relatório não são salvas no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="d8fed-114">Modifications that you make locally to the report definition are not saved on the report server.</span></span>

         <span data-ttu-id="d8fed-115">Ou, para atualizar a definição de relatório de um arquivo. RDL, clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="d8fed-115">Or, to update the report definition from an .rdl file, click **Update**.</span></span>

        > [!NOTE]
        >  <span data-ttu-id="d8fed-116">Se você atualizar uma definição de relatório, deverá redefinir as definições de fonte de dados depois de a atualização ser concluída.</span><span class="sxs-lookup"><span data-stu-id="d8fed-116">If you update a report definition, you must reset the data source settings after the update is completed.</span></span>

    -   <span data-ttu-id="d8fed-117">Use os botões **excluir** ou **mover** para excluir ou mover o relatório.</span><span class="sxs-lookup"><span data-stu-id="d8fed-117">Use the **Delete** or **Move** buttons to delete or move the report.</span></span>

    -   <span data-ttu-id="d8fed-118">Você também pode criar um relatório vinculado.</span><span class="sxs-lookup"><span data-stu-id="d8fed-118">You can also create a linked report.</span></span>

5.  <span data-ttu-id="d8fed-119">Quando terminar de configurar as propriedades gerais para o relatório, clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="d8fed-119">When you have finished configuring general properties for the report, click **Apply**.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8fed-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d8fed-120">See Also</span></span>
 <span data-ttu-id="d8fed-121">[Mover ou excluir um Item &#40;Report Manager](report-server/move-or-delete-an-item-report-manager.md) [página&#41;conteúdo &#40;](../../2014/reporting-services/contents-page-report-manager.md) Report Manager&#41;[Localizar, exibir e gerenciar relatórios &#40;Construtor de relatórios e SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) [página Propriedades gerais, relatórios &#40;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) Report Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="d8fed-121">[Move or Delete an Item &#40;Report Manager&#41;](report-server/move-or-delete-an-item-report-manager.md) [Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) [Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) [General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md)</span></span>


