---
title: Página novo relatório vinculado (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fefb46e8-6901-4d50-a3f8-7c49ad72e7b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61138e51cfd9bb6e1ee124dd4aa3bc224d8aebcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576242"
---
# <a name="new-linked-report-page-report-manager"></a><span data-ttu-id="f6d46-102">Página Novo Relatório Vinculado (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="f6d46-102">New Linked Report Page (Report Manager)</span></span>
  <span data-ttu-id="f6d46-103">Use a página Novo Relatório Vinculado para criar um relatório vinculado.</span><span class="sxs-lookup"><span data-stu-id="f6d46-103">Use the New Linked Report page to create a linked report.</span></span> <span data-ttu-id="f6d46-104">Um relatório vinculado é um relatório com configurações e propriedades próprias, mas vincula à definição de relatório de outro relatório.</span><span class="sxs-lookup"><span data-stu-id="f6d46-104">A linked report is a report with settings and properties of its own, but links to the report definition of another report.</span></span> <span data-ttu-id="f6d46-105">Relatórios vinculados são úteis quando você tem um relatório padrão que deseja variar para grupos ou usuários específicos; por exemplo, um relatório regional que retorna dados diferentes com base em um código regional especificado como parâmetro.</span><span class="sxs-lookup"><span data-stu-id="f6d46-105">Linked reports are useful when you have a base report that you want to vary for specific groups or users; for example, a regional report that returns different data based on a regional code that you specify as a parameter.</span></span> <span data-ttu-id="f6d46-106">Geralmente, um relatório vinculado é criado a partir um relatório com parâmetros quando você deseja variar e salvar valores de parâmetro diferentes com cada instância de relatório.</span><span class="sxs-lookup"><span data-stu-id="f6d46-106">A linked report is typically created from a parameterized report when you want to vary and then save different parameter values with each report instance.</span></span> <span data-ttu-id="f6d46-107">Porém, você pode criar um relatório vinculado de qualquer relatório ao qual tenha acesso.</span><span class="sxs-lookup"><span data-stu-id="f6d46-107">However, you can create a linked report from any report to which you have access.</span></span>  
  
 <span data-ttu-id="f6d46-108">Um relatório vinculado pode ter seu próprio nome, descrição, local, propriedades de parâmetro, propriedades de histórico de execução de relatório, permissões e assinaturas.</span><span class="sxs-lookup"><span data-stu-id="f6d46-108">A linked report can have its own name, description, location, parameter properties, report execution properties, report history properties, permissions, and subscriptions.</span></span> <span data-ttu-id="f6d46-109">No entanto, um relatório vinculado deve usar as propriedades de fonte de dados e o layout do relatório padrão que fornece a definição do relatório.</span><span class="sxs-lookup"><span data-stu-id="f6d46-109">However, a linked report must use the data source properties and layout of the base report that provides the report definition.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="f6d46-110">Navegação</span><span class="sxs-lookup"><span data-stu-id="f6d46-110">Navigation</span></span>  
 <span data-ttu-id="f6d46-111">Use os procedimentos a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="f6d46-111">Use the following procedures to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-linked-report-page-from-the-contents-page"></a><span data-ttu-id="f6d46-112">Para abrir a página Novo Relatório Vinculado na página Conteúdo</span><span class="sxs-lookup"><span data-stu-id="f6d46-112">To open the New Linked Report page from the Contents page</span></span>  
  
1.  <span data-ttu-id="f6d46-113">Abra o Gerenciador de Relatórios e localize um relatório para o qual você deseja criar um relatório vinculado.</span><span class="sxs-lookup"><span data-stu-id="f6d46-113">Open Report Manager, and locate a report for which you want to create a linked report.</span></span>  
  
2.  <span data-ttu-id="f6d46-114">Focalize o relatório e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="f6d46-114">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="f6d46-115">No menu suspenso, clique em **Criar Relatório Vinculado**.</span><span class="sxs-lookup"><span data-stu-id="f6d46-115">In the drop-down menu, click **Create Linked Report**.</span></span>  
  
###### <a name="to-open-the-new-linked-report-page-from-the-general-properties-page-of-a-report"></a><span data-ttu-id="f6d46-116">Para abrir a página Novo Relatório Vinculado na página de Propriedades gerais de um relatório.</span><span class="sxs-lookup"><span data-stu-id="f6d46-116">To open the New Linked Report page from the General properties page of a report</span></span>  
  
1.  <span data-ttu-id="f6d46-117">Abra o Gerenciador de Relatórios e localize um relatório para o qual você deseja criar um relatório vinculado.</span><span class="sxs-lookup"><span data-stu-id="f6d46-117">Open Report Manager, and locate a report for which you want to create a linked report.</span></span>  
  
2.  <span data-ttu-id="f6d46-118">Focalize o relatório e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="f6d46-118">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="f6d46-119">No menu suspenso, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="f6d46-119">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="f6d46-120">Esse procedimento abre a página de propriedades Geral do relatório.</span><span class="sxs-lookup"><span data-stu-id="f6d46-120">This opens the General properties page for the report.</span></span>  
  
4.  <span data-ttu-id="f6d46-121">Na barra de ferramentas de item, clique em **Criar Relatório Vinculado**.</span><span class="sxs-lookup"><span data-stu-id="f6d46-121">In the item toolbar, click **Create Linked Report**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f6d46-122">Opções</span><span class="sxs-lookup"><span data-stu-id="f6d46-122">Options</span></span>  
 <span data-ttu-id="f6d46-123">**Nome**</span><span class="sxs-lookup"><span data-stu-id="f6d46-123">**Name**</span></span>  
 <span data-ttu-id="f6d46-124">Especifique o nome do relatório vinculado.</span><span class="sxs-lookup"><span data-stu-id="f6d46-124">Specify the name of the linked report.</span></span> <span data-ttu-id="f6d46-125">Um nome deve conter pelo menos um caractere alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="f6d46-125">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="f6d46-126">Também pode conter espaços e certos símbolos.</span><span class="sxs-lookup"><span data-stu-id="f6d46-126">It can also include spaces and certain symbols.</span></span> <span data-ttu-id="f6d46-127">Porém, você não deve usar os caracteres; ?</span><span class="sxs-lookup"><span data-stu-id="f6d46-127">However, you must not use the characters ; ?</span></span> <span data-ttu-id="f6d46-128">: \@ & = +, $/\* \< > | "or/ao especificar um nome.</span><span class="sxs-lookup"><span data-stu-id="f6d46-128">: \@ & = + , $ / \* \< > | " or / when specifying a name.</span></span>  
  
 <span data-ttu-id="f6d46-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f6d46-129">**Description**</span></span>  
 <span data-ttu-id="f6d46-130">Digite uma descrição do conteúdo do relatório.</span><span class="sxs-lookup"><span data-stu-id="f6d46-130">Type a description of the report contents.</span></span> <span data-ttu-id="f6d46-131">Essa descrição aparece na página Conteúdo para usuários com permissão para acessar o relatório.</span><span class="sxs-lookup"><span data-stu-id="f6d46-131">This description appears in the Contents page to users who have permission to access the report.</span></span>  
  
 <span data-ttu-id="f6d46-132">**Localidade**</span><span class="sxs-lookup"><span data-stu-id="f6d46-132">**Location**</span></span>  
 <span data-ttu-id="f6d46-133">Especifique o caminho de pasta que contém o relatório.</span><span class="sxs-lookup"><span data-stu-id="f6d46-133">Specify the folder path that contains the report.</span></span> <span data-ttu-id="f6d46-134">Por padrão, relatórios vinculados são criados como irmãos para o relatório padrão.</span><span class="sxs-lookup"><span data-stu-id="f6d46-134">By default, linked reports are created as siblings to the base report.</span></span> <span data-ttu-id="f6d46-135">Clique em **Alterar Local** para colocar o relatório vinculado em uma pasta diferente.</span><span class="sxs-lookup"><span data-stu-id="f6d46-135">Click **Change Location** to put the linked report in a different folder.</span></span>  
  
 <span data-ttu-id="f6d46-136">**OK**</span><span class="sxs-lookup"><span data-stu-id="f6d46-136">**OK**</span></span>  
 <span data-ttu-id="f6d46-137">Clique em **OK** para salvar suas alterações e voltar à página de propriedades Geral do relatório padrão.</span><span class="sxs-lookup"><span data-stu-id="f6d46-137">Click **OK** to save your changes and return to the General properties page of the base report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6d46-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f6d46-138">See Also</span></span>  
 <span data-ttu-id="f6d46-139">[Criar um relatório vinculado](reports/create-a-linked-report.md) </span><span class="sxs-lookup"><span data-stu-id="f6d46-139">[Create a Linked Report](reports/create-a-linked-report.md) </span></span>  
 <span data-ttu-id="f6d46-140">[Página Propriedades gerais, relatórios &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="f6d46-140">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 [<span data-ttu-id="f6d46-141">Ajuda F1 do Gerenciador de Relatórios</span><span class="sxs-lookup"><span data-stu-id="f6d46-141">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
