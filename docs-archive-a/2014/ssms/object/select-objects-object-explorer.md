---
title: Selecionar objetos (Pesquisador de Objetos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.selectobjects.f1
ms.assetid: 692477fe-dd7c-403d-acd2-bb108b6077f1
author: stevestein
ms.author: sstein
ms.openlocfilehash: ceec604d9fe07b339af11ed69226d41a7f616678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678545"
---
# <a name="select-objects-object-explorer"></a><span data-ttu-id="9c713-102">Selecionar objetos (Pesquisador de Objetos)</span><span class="sxs-lookup"><span data-stu-id="9c713-102">Select Objects (Object Explorer)</span></span>
  <span data-ttu-id="9c713-103">Use a caixa de diálogo **Selecionar Objetos** para adicionar um objeto a uma lista em outra caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9c713-103">Use the **Select Objects** dialog box to add an object to a list in another dialog box.</span></span> <span data-ttu-id="9c713-104">O título da caixa de diálogo e as opções disponíveis na caixa de diálogo dependem de como foram abertos.</span><span class="sxs-lookup"><span data-stu-id="9c713-104">The dialog box title and the options available in the dialog box depend upon how it was opened.</span></span> <span data-ttu-id="9c713-105">Aparecerão somente opções disponíveis; por exemplo, só estão disponíveis logons quando você está selecionando um proprietário para um objeto novo.</span><span class="sxs-lookup"><span data-stu-id="9c713-105">Only available options appear; for instance, only logins are available when you are selecting an owner for a new object.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9c713-106">Opções</span><span class="sxs-lookup"><span data-stu-id="9c713-106">Options</span></span>  
 <span data-ttu-id="9c713-107">**Selecionar esses tipos de objeto**</span><span class="sxs-lookup"><span data-stu-id="9c713-107">**Select these object types**</span></span>  
 <span data-ttu-id="9c713-108">Exibe uma lista dos tipos aos quais pertencem os objetos a ser selecionados.</span><span class="sxs-lookup"><span data-stu-id="9c713-108">Displays a list of the types of which the objects to be selected belong.</span></span> <span data-ttu-id="9c713-109">Os tipos incluem entidades de segurança e protegíveis no nível do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9c713-109">The types include [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] level and database level principals and securables.</span></span> <span data-ttu-id="9c713-110">Essa caixa é preenchida com as seleções feitas na caixa de diálogo **Selecionar Tipos de Objeto** , acessada do botão **Tipo de Objetos** .</span><span class="sxs-lookup"><span data-stu-id="9c713-110">This box is populated from the selections made from the **Select Object Types** dialog box, accessed from the **Objects Type** button.</span></span>  
  
 <span data-ttu-id="9c713-111">**Digite os nomes de objeto a selecionar**</span><span class="sxs-lookup"><span data-stu-id="9c713-111">**Enter the object names to select**</span></span>  
 <span data-ttu-id="9c713-112">Digite uma lista separada por ponto-e-vírgula com os nomes dos objetos a ser selecionados.</span><span class="sxs-lookup"><span data-stu-id="9c713-112">Enter a semicolon-separated list of names of the objects to be selected.</span></span> <span data-ttu-id="9c713-113">Os objetos a serem selecionados devem ser de um tipo listado na caixa **Selecionar esses tipos de objeto** .</span><span class="sxs-lookup"><span data-stu-id="9c713-113">Objects to be selected must be of a type listed in the **Select these object types** box.</span></span> <span data-ttu-id="9c713-114">Os objetos podem ser selecionados de uma lista acessada clicando no botão **Procurar** .</span><span class="sxs-lookup"><span data-stu-id="9c713-114">Objects can be selected from a list accessed by clicking the **Browse** button.</span></span>  
  
 <span data-ttu-id="9c713-115">**Tipos de Objeto**</span><span class="sxs-lookup"><span data-stu-id="9c713-115">**Object Types**</span></span>  
 <span data-ttu-id="9c713-116">Exibe uma lista de tipos de objeto.</span><span class="sxs-lookup"><span data-stu-id="9c713-116">Displays a list of object types.</span></span> <span data-ttu-id="9c713-117">Selecione um ou mais marcando a caixa de seleção que corresponde ao tipo.</span><span class="sxs-lookup"><span data-stu-id="9c713-117">Select one or more by selecting the check box corresponding to the type.</span></span>  
  
 <span data-ttu-id="9c713-118">**Verificar Nomes**</span><span class="sxs-lookup"><span data-stu-id="9c713-118">**Check Names**</span></span>  
 <span data-ttu-id="9c713-119">Valida os nomes de objeto na caixa **Digitar os nomes de objeto a selecionar** .</span><span class="sxs-lookup"><span data-stu-id="9c713-119">Validates the object names in the **Enter the object names to select** box.</span></span> <span data-ttu-id="9c713-120">Se for listado um nome de objeto inválido, será mostrada a caixa de diálogo **Nome não Encontrado** .</span><span class="sxs-lookup"><span data-stu-id="9c713-120">If an object name that is not valid is listed, the **Name not Found** dialog box is presented.</span></span> <span data-ttu-id="9c713-121">Com essa caixa de diálogo, o nome pode ser corrigido ou removido da lista de objetos a selecionar.</span><span class="sxs-lookup"><span data-stu-id="9c713-121">With this dialog box, the name can be corrected or removed from the list of objects to select.</span></span>  
  
 <span data-ttu-id="9c713-122">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="9c713-122">**Browse**</span></span>  
 <span data-ttu-id="9c713-123">Mostra a caixa de diálogo **Procurar por Objetos** .</span><span class="sxs-lookup"><span data-stu-id="9c713-123">Presents the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="9c713-124">Ela contém uma lista de objetos dos tipos listados na caixa **Selecionar Esses Tipos de Objeto** .</span><span class="sxs-lookup"><span data-stu-id="9c713-124">This contains a list of objects of the types listed in the **Select These Object Types** box.</span></span> <span data-ttu-id="9c713-125">Selecione os objetos dessa lista marcando as caixas de seleção correspondentes.</span><span class="sxs-lookup"><span data-stu-id="9c713-125">Select objects from this list by selecting the corresponding check boxes.</span></span>  
  
  
