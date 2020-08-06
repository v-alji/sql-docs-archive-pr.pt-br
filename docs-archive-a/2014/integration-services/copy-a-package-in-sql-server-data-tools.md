---
title: Copiar um pacote no SQL Server Data Tools | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], copying
- copying packages
- regenerating package GUID
- updating package properties
ms.assetid: 03edc659-e76d-48c0-a749-5f1899b6b507
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bd6ed4dd66ee4755181f5df6f3c1b5466b3f26b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574841"
---
# <a name="copy-a-package-in-sql-server-data-tools"></a><span data-ttu-id="8dc76-102">Copiar um pacote nas Ferramentas de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="8dc76-102">Copy a Package in SQL Server Data Tools</span></span>
  <span data-ttu-id="8dc76-103">Este descreve como criar um novo pacote do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] por meio da cópia de um pacote existente e como atualizar as propriedades `Name` e `GUID` do novo pacote.</span><span class="sxs-lookup"><span data-stu-id="8dc76-103">This topic describes how to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package by copying an existing package, and how to update the `Name` and `GUID` properties of the new package.</span></span>  
  
### <a name="to-copy-a-package"></a><span data-ttu-id="8dc76-104">Para copiar um pacote</span><span class="sxs-lookup"><span data-stu-id="8dc76-104">To copy a package</span></span>  
  
1.  <span data-ttu-id="8dc76-105">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contém o pacote que deseja copiar.</span><span class="sxs-lookup"><span data-stu-id="8dc76-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package that you want to copy.</span></span>  
  
2.  <span data-ttu-id="8dc76-106">No Gerenciador de Soluções, clique duas vezes no pacote.</span><span class="sxs-lookup"><span data-stu-id="8dc76-106">In Solution Explorer, double-click the package.</span></span>  
  
3.  <span data-ttu-id="8dc76-107">Verifique se o pacote que será copiado está selecionado no Gerenciador de Soluções ou a guia no Designer SSIS que contém o pacote é a guia ativa</span><span class="sxs-lookup"><span data-stu-id="8dc76-107">Verify either the package to copy is selected in Solution Explorer or the tab in SSIS Designer that contains the package is the active tab</span></span>  
  
4.  <span data-ttu-id="8dc76-108">No menu **Arquivo** , clique em **Salvar \<package name> como**.</span><span class="sxs-lookup"><span data-stu-id="8dc76-108">On the **File** menu, click **Save \<package name> As**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8dc76-109">O pacote deve ser aberto no Designer do SSIS antes que a opção **Salvar Como** aparecer no menu **Arquivo** .</span><span class="sxs-lookup"><span data-stu-id="8dc76-109">The package must be opened in SSIS Designer before the **Save As** option appears on the **File** menu.</span></span>  
  
5.  <span data-ttu-id="8dc76-110">Como opção, navegue até uma pasta diferente.</span><span class="sxs-lookup"><span data-stu-id="8dc76-110">Optionally, browse to a different folder.</span></span>  
  
6.  <span data-ttu-id="8dc76-111">Atualize o nome do arquivo do pacote.</span><span class="sxs-lookup"><span data-stu-id="8dc76-111">Update the name of the package file.</span></span> <span data-ttu-id="8dc76-112">Lembre-se de manter a extensão de arquivo .dtsx.</span><span class="sxs-lookup"><span data-stu-id="8dc76-112">Make sure that you retain the .dtsx file extension.</span></span>  
  
7.  <span data-ttu-id="8dc76-113">Clique em **Save** (Salvar).</span><span class="sxs-lookup"><span data-stu-id="8dc76-113">Click **Save**.</span></span>  
  
8.  <span data-ttu-id="8dc76-114">No prompt, escolha se deseja atualizar o nome do objeto de pacote para corresponder ao nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="8dc76-114">At the prompt, choose whether to update the name of the package object to match the file name.</span></span> <span data-ttu-id="8dc76-115">Se você clicar em **Sim**, a `Name` Propriedade do pacote será atualizada.</span><span class="sxs-lookup"><span data-stu-id="8dc76-115">If you click **Yes**, the `Name` property of the package is updated.</span></span> <span data-ttu-id="8dc76-116">O novo pacote é adicionado ao projeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e aberto no Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8dc76-116">The new package is added to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and opened in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
9. <span data-ttu-id="8dc76-117">Como opção, clique no plano de fundo da guia **Fluxo de Controle** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8dc76-117">Optionally, click in the background of the **Control Flow** tab, and the click **Properties**.</span></span>  
  
10. <span data-ttu-id="8dc76-118">Na janela Propriedades, clique no valor da propriedade ID e, na lista suspensa, clique em **\<Generate New ID>** .</span><span class="sxs-lookup"><span data-stu-id="8dc76-118">In the Properties window, click the value of the ID property, and then in the drop-down list click **\<Generate New ID>**.</span></span>  
  
11. <span data-ttu-id="8dc76-119">No menu **Arquivo** , clique em **Salvar Itens Selecionados** para salvar o novo pacote.</span><span class="sxs-lookup"><span data-stu-id="8dc76-119">On the **File** menu, click **Save Selected Items** to save the new package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dc76-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8dc76-120">See Also</span></span>  
 <span data-ttu-id="8dc76-121">[Salvar uma cópia de um pacote](../../2014/integration-services/save-a-copy-of-a-package.md) </span><span class="sxs-lookup"><span data-stu-id="8dc76-121">[Save a Copy of a Package](../../2014/integration-services/save-a-copy-of-a-package.md) </span></span>  
 <span data-ttu-id="8dc76-122">[Criar pacotes no SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="8dc76-122">[Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span></span>  
 [<span data-ttu-id="8dc76-123">Pacotes do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8dc76-123">Integration Services &#40;SSIS&#41; Packages</span></span>](../../2014/integration-services/integration-services-ssis-packages.md)  
  
  
