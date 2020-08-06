---
title: Salvar um pacote como um modelo de pacote | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- reusing packages
- templates [Integration Services]
ms.assetid: efe66cec-3933-4f6e-8d35-fe3d300de66c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 30bddb5a343e7c7aef279bc66c25be30a2cf1a12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680028"
---
# <a name="save-a-package-as-a-package-template"></a><span data-ttu-id="1d9c8-102">Salvar um pacote como um modelo de pacote</span><span class="sxs-lookup"><span data-stu-id="1d9c8-102">Save a Package as a Package Template</span></span>
  <span data-ttu-id="1d9c8-103">Este tópico descreve como designar e usar pacotes personalizados como modelos para criar novos pacotes do Integration Services no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d9c8-103">This topic describes how to designate and use custom packages as templates when you create new Integration Services packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="1d9c8-104">Por padrão, o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] usa um modelo de pacote que cria um pacote vazio quando você adiciona um novo pacote a um projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d9c8-104">By default, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] uses a package template that creates an empty package when you add a new package to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="1d9c8-105">Você não pode substituir este modelo padrão, mas pode adicionar novos modelos.</span><span class="sxs-lookup"><span data-stu-id="1d9c8-105">You cannot replace this default template, but you can add new templates.</span></span>  
  
 <span data-ttu-id="1d9c8-106">Você pode designar vários pacotes para serem usados como modelos.</span><span class="sxs-lookup"><span data-stu-id="1d9c8-106">You can designate multiple packages to use as templates.</span></span> <span data-ttu-id="1d9c8-107">Antes de implementar os pacotes personalizados como modelos, é preciso criá-los.</span><span class="sxs-lookup"><span data-stu-id="1d9c8-107">Before you can implement custom packages as templates, you must create the packages.</span></span>  
  
 <span data-ttu-id="1d9c8-108">Ao criar um pacote usando os pacotes personalizados como modelos, os novos pacotes apresentam o mesmo nome e GUID do modelo.</span><span class="sxs-lookup"><span data-stu-id="1d9c8-108">When you create package using custom packages as templates, the new packages have the same name and GUID as the template.</span></span> <span data-ttu-id="1d9c8-109">Para obter a diferenciação dos pacotes, atualize o valor da propriedade `Name` e gere uma nova GUID para a propriedade `ID`.</span><span class="sxs-lookup"><span data-stu-id="1d9c8-109">To differentiate among packages you should update the value of the `Name` property and generate a new GUID for the `ID` property.</span></span> <span data-ttu-id="1d9c8-110">Para obter mais informações, consulte [Criar pacotes no SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) e [Definir Propriedades de Pacote](set-package-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1d9c8-110">For more information, see [Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) and [Set Package Properties](set-package-properties.md).</span></span>  
  
### <a name="to-designate-a-custom-package-as-a-package-template"></a><span data-ttu-id="1d9c8-111">Para designar um pacote personalizado como um modelo de pacote</span><span class="sxs-lookup"><span data-stu-id="1d9c8-111">To designate a custom package as a package template</span></span>  
  
1.  <span data-ttu-id="1d9c8-112">No sistema de arquivos, localize o pacote que deseja usar como modelo.</span><span class="sxs-lookup"><span data-stu-id="1d9c8-112">In the file system, locate the package that you want to use as template.</span></span>  
  
2.  <span data-ttu-id="1d9c8-113">Copie o pacote para a pasta DataTransformationItems.</span><span class="sxs-lookup"><span data-stu-id="1d9c8-113">Copy the package to the DataTransformationItems folder.</span></span> <span data-ttu-id="1d9c8-114">Por padrão, esta pasta está em C:\Arquivos de Programas\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\ProjectItems\DataTransformationProject.</span><span class="sxs-lookup"><span data-stu-id="1d9c8-114">By default this folder is in C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\ProjectItems\DataTransformationProject.</span></span>  
  
3.  <span data-ttu-id="1d9c8-115">Repita as etapas 1 e 2 para cada pacote que quiser usar como modelo.</span><span class="sxs-lookup"><span data-stu-id="1d9c8-115">Repeat steps 1 and 2 for each package that you want to use as a template.</span></span>  
  
### <a name="to-use-a-custom-package-as-a-package-template"></a><span data-ttu-id="1d9c8-116">Para usar um pacote personalizado como um modelo de pacote</span><span class="sxs-lookup"><span data-stu-id="1d9c8-116">To use a custom package as a package template</span></span>  
  
1.  <span data-ttu-id="1d9c8-117">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no qual você deseja criar um pacote.</span><span class="sxs-lookup"><span data-stu-id="1d9c8-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in which you want to create a package.</span></span>  
  
2.  <span data-ttu-id="1d9c8-118">No Gerenciador de Soluções, clique com o botão direito do mouse no projeto, aponte para **Adicionar** e clique em **Novo Item**.</span><span class="sxs-lookup"><span data-stu-id="1d9c8-118">In Solution Explorer, right-click the project, point to **Add**, and then click **New Item**.</span></span>  
  
3.  <span data-ttu-id="1d9c8-119">Na caixa de diálogo **Adicionar Novo Item - \<project name>** , clique no pacote que deseja usar como modelo.</span><span class="sxs-lookup"><span data-stu-id="1d9c8-119">In the **Add New Item -\<project name>** dialog box, click the package that you want to use as a template.</span></span>  
  
     <span data-ttu-id="1d9c8-120">A lista de modelos inclui o modelo padrão do pacote chamado Novo Pacote SSIS.</span><span class="sxs-lookup"><span data-stu-id="1d9c8-120">The list of templates includes the default package template named New SSIS Package.</span></span> <span data-ttu-id="1d9c8-121">O ícone do pacote identifica os modelos que podem ser usados como modelos de pacote.</span><span class="sxs-lookup"><span data-stu-id="1d9c8-121">The package icon identifies templates that can be used as package templates.</span></span>  
  
4.  <span data-ttu-id="1d9c8-122">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1d9c8-122">Click **Add**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d9c8-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1d9c8-123">See Also</span></span>  
 <span data-ttu-id="1d9c8-124">[Criar pacotes no SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1d9c8-124">[Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span></span>  
 [<span data-ttu-id="1d9c8-125">Pacotes do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1d9c8-125">Integration Services &#40;SSIS&#41; Packages</span></span>](../../2014/integration-services/integration-services-ssis-packages.md)  
  
  
