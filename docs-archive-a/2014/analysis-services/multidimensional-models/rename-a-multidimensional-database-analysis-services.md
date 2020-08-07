---
title: Renomear um banco de dados multidimensional (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- renaming databases
ms.assetid: 15fdaec7-f3e4-44d9-9b78-1a1d78c484e0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3974e7671aff5d1cba22b10563bbc85a129a1dff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575408"
---
# <a name="rename-a-multidimensional-database-analysis-services"></a><span data-ttu-id="f6899-102">Renomear um bancos de dados multidimensional (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="f6899-102">Rename a Multidimensional Database (Analysis Services)</span></span>
  <span data-ttu-id="f6899-103">A maneira como você altera o nome de um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] banco de dados depende de como você se conecta ao [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f6899-103">The manner in which you change the name of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database depends upon how you connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="f6899-104">Para alterar o nome de um banco de dados existente, conecte-se em modo online.</span><span class="sxs-lookup"><span data-stu-id="f6899-104">To change the name of an existing database, you must connect in online mode.</span></span> <span data-ttu-id="f6899-105">Para alterar o nome do banco de dados no qual os objetos de um projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] serão instanciados, conecte-se em modo de projeto.</span><span class="sxs-lookup"><span data-stu-id="f6899-105">To change the name of the database into which objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project will be instantiated, you must connect in project mode.</span></span>  
  
### <a name="to-change-the-database-name-in-online-mode"></a><span data-ttu-id="f6899-106">Alterar o nome do banco de dados em modo online</span><span class="sxs-lookup"><span data-stu-id="f6899-106">To change the database name in online mode</span></span>  
  
1.  <span data-ttu-id="f6899-107">Usando o [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], conecte-se diretamente ao banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6899-107">Using [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], connect directly to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="f6899-108">No Gerenciador de Soluções, clique com o botão direito do mouse no banco de dados e clique em **Editar Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="f6899-108">In Solution Explorer, right-click the database and then click **Edit Database**.</span></span>  
  
3.  <span data-ttu-id="f6899-109">Na caixa de texto **Nome do Banco de Dados** , altere o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f6899-109">In the **Database name** text box, change the database name.</span></span>  
  
4.  <span data-ttu-id="f6899-110">Clique em **Salvar** ou em **Salvar Tudo** na barra de ferramentas, clique em **Salvar Itens Selecionados** ou em **Salvar Tudo** no menu **Arquivo** ou feche o **Designer de Banco de Dados** e, em seguida, clique em **Salvar** quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="f6899-110">Click **Save** or **Save All** on the toolbar, click **Save Selected Items** or **Save All** on the **File** menu, or close the **Database Designer** and then click **Save** when prompted.</span></span>  
  
     <span data-ttu-id="f6899-111">O nome de banco de dados é atualizado na instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , bem como o objeto de banco de dados no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="f6899-111">The database name is updated in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and the database object in Solution Explorer is refreshed.</span></span>  
  
### <a name="to-change-the-database-name-in-project-mode"></a><span data-ttu-id="f6899-112">Alterar o nome do banco de dados em modo de projeto</span><span class="sxs-lookup"><span data-stu-id="f6899-112">To change the database name in project mode</span></span>  
  
1.  <span data-ttu-id="f6899-113">Abra o projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6899-113">Open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="f6899-114">No Gerenciador de Soluções, clique com o botão direito do mouse no projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f6899-114">In Solution Explorer, right-click the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="f6899-115">Na caixa de diálogo **Páginas de Propriedades** , clique em **Implantação** na seção **Propriedades de Configuração** .</span><span class="sxs-lookup"><span data-stu-id="f6899-115">In the **Property Pages** dialog box, click **Deployment** in the **Configuration Properties** section.</span></span>  
  
4.  <span data-ttu-id="f6899-116">Altere a propriedade **Banco de Dados** com o novo nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f6899-116">Change the **Database** property to the new database name.</span></span>  
  
     <span data-ttu-id="f6899-117">Na próxima vez que o projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] for implantado, ele será implantado com esse novo nome de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f6899-117">The next time the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project is deployed, it will be deployed to this new database name.</span></span> <span data-ttu-id="f6899-118">Se existir um banco de dados com o mesmo nome, ele será substituído.</span><span class="sxs-lookup"><span data-stu-id="f6899-118">If this database already exists, it will be overwritten.</span></span>  
  
### <a name="to-change-the-database-name-using-sql-server-management-studio"></a><span data-ttu-id="f6899-119">Para alterar o nome do banco de dados usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f6899-119">To change the database name using SQL Server Management Studio</span></span>  
  
-   <span data-ttu-id="f6899-120">Clique com o botão direito do mouse no banco de dados [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e edite a propriedade Name.</span><span class="sxs-lookup"><span data-stu-id="f6899-120">Right-click the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database and edit the Name property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6899-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f6899-121">See Also</span></span>  
 <span data-ttu-id="f6899-122">[Configurar propriedades do servidor no Analysis Services](../server-properties/server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="f6899-122">[Configure Server Properties in Analysis Services](../server-properties/server-properties-in-analysis-services.md) </span></span>  
 <span data-ttu-id="f6899-123">[Definir propriedades de banco de dados multidimensional &#40;Analysis Services&#41;](set-multidimensional-database-properties-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="f6899-123">[Set Multidimensional Database Properties &#40;Analysis Services&#41;](set-multidimensional-database-properties-analysis-services.md) </span></span>  
 <span data-ttu-id="f6899-124">[Configurar propriedades do projeto de Analysis Services &#40;SSDT&#41;](configure-analysis-services-project-properties-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="f6899-124">[Configure Analysis Services Project Properties &#40;SSDT&#41;](configure-analysis-services-project-properties-ssdt.md) </span></span>  
 [<span data-ttu-id="f6899-125">Implantar projetos do Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="f6899-125">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](deploy-analysis-services-projects-ssdt.md)  
  
  
