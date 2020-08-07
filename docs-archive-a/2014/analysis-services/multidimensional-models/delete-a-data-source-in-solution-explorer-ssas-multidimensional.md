---
title: Excluir uma fonte de dados em Gerenciador de Soluções (SSAS multidimensional) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.deleteobjects.f1
helpviewer_keywords:
- data sources [Analysis Services], deleting
- deleting data sources
- removing data sources
ms.assetid: b45441ef-f909-4736-98b9-cc80d0acac99
author: minewiskan
ms.author: owend
ms.openlocfilehash: d6101c8704579894590994d88e0286197148b694
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583200"
---
# <a name="delete-a-data-source-in-solution-explorer-ssas-multidimensional"></a><span data-ttu-id="6b2de-102">excluir uma exibição da fonte de dados no gerenciador de soluções (SSAS multidimensional)</span><span class="sxs-lookup"><span data-stu-id="6b2de-102">Delete a Data Source in Solution Explorer (SSAS Multidimensional)</span></span>
  <span data-ttu-id="6b2de-103">Você pode excluir um objeto de fonte de dados para removê-lo permanentemente de um projeto de modelo multidimensional do Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="6b2de-103">You can delete a data source object to permanently remove it from an Analysis Services multidimensional model project.</span></span>  
  
 <span data-ttu-id="6b2de-104">No [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], as fontes de dados são a base para a criação de exibições de dados e as exibições da fonte de dados, por sua vez, são utilizadas para definir dimensões, cubos e estruturas de mineração em um projeto ou banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b2de-104">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], data sources provide the basis on which data source views are constructed, and data source views are in turn used to define dimensions, cubes, and mining structures in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database.</span></span> <span data-ttu-id="6b2de-105">Portanto, a exclusão de uma fonte de dados pode invalidar outros objetos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de um projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b2de-105">Therefore, deleting a data source may invalidate other [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="6b2de-106">Você sempre deve analisar a lista de objetos dependentes que é fornecida antes de excluir o objeto.</span><span class="sxs-lookup"><span data-stu-id="6b2de-106">You should always review the list of dependent objects that is provided before deleting the object.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6b2de-107">As fontes de dados das quais outros objetos dependem não podem ser excluídas de um banco de dados aberto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pelo [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] em modo online.</span><span class="sxs-lookup"><span data-stu-id="6b2de-107">Data sources on which other objects depend cannot be deleted from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database opened by [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span> <span data-ttu-id="6b2de-108">É preciso excluir todos os objetos do banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que dependem dessa fonte de dados antes de excluí-la.</span><span class="sxs-lookup"><span data-stu-id="6b2de-108">You must delete all objects in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that depend on that data source before deleting the data source.</span></span> <span data-ttu-id="6b2de-109">Para obter mais informações, consulte [Conectar em Modo Online a um Banco de Dados do Analysis Services](connect-in-online-mode-to-an-analysis-services-database.md).</span><span class="sxs-lookup"><span data-stu-id="6b2de-109">For more information about online mode, see [Connect in Online Mode to an Analysis Services Database](connect-in-online-mode-to-an-analysis-services-database.md).</span></span>  
  
### <a name="to-delete-a-data-source"></a><span data-ttu-id="6b2de-110">Para excluir uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="6b2de-110">To delete a data source</span></span>  
  
1.  <span data-ttu-id="6b2de-111">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto ou conecte-se ao banco de dados do qual você deseja excluir uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="6b2de-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database from which you want to delete a data source.</span></span>  
  
2.  <span data-ttu-id="6b2de-112">No **Gerenciador de Soluções**, expanda a pasta **Fontes de Dados** .</span><span class="sxs-lookup"><span data-stu-id="6b2de-112">In **Solution Explorer**, expand the **Data Sources** folder.</span></span>  
  
3.  <span data-ttu-id="6b2de-113">Clique com o botão direito do mouse na fonte de dados e, em seguida, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="6b2de-113">Right-click the data source, and then click **Delete**.</span></span> <span data-ttu-id="6b2de-114">A caixa de diálogo **Excluir Objetos**  aparecerá, mostrando os objetos que serão invalidados se você excluir a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="6b2de-114">The **Delete Objects**  dialog box appears, showing the objects that will be invalidated if you delete the data source.</span></span> <span data-ttu-id="6b2de-115">Examine esta lista com cuidado antes de clicar em **OK** para excluir a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="6b2de-115">Review this list carefully before clicking **OK** to delete the data source.</span></span>  
  
4.  <span data-ttu-id="6b2de-116">Salve o projeto.</span><span class="sxs-lookup"><span data-stu-id="6b2de-116">Save the project.</span></span>  
  
     <span data-ttu-id="6b2de-117">Depois de excluir uma fonte de dados de um projeto do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , salve o projeto modificado ou você verá um erro na próxima vez que abrir o projeto, pois faltará o arquivo XML subjacente da fonte de dados excluída quando o projeto tentar carregá-la.</span><span class="sxs-lookup"><span data-stu-id="6b2de-117">After deleting a data source from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you must save the modified project or you will receive an error the next time you open the project because the underlying XML file for the deleted data source will be missing when the project attempts to load the deleted data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b2de-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6b2de-118">See Also</span></span>  
 <span data-ttu-id="6b2de-119">[Fontes de dados em modelos multidimensionais](data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="6b2de-119">[Data Sources in Multidimensional Models](data-sources-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="6b2de-120">Fontes de dados com suporte &#40;SSAS multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="6b2de-120">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](supported-data-sources-ssas-multidimensional.md)  
  
  
