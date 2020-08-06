---
title: Reutilização de objetos do pacote | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- GUID regenerating [Integration Services]
- reusing packages
- templates [Integration Services]
- copying packages
- regenerating package GUID
ms.assetid: 08f723bf-15b5-44bd-9a46-04e8781bfbfb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b7612cb2684bb842108068b062e54fbe9dee4327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679409"
---
# <a name="reuse-of-package-objects"></a><span data-ttu-id="66e0d-102">Reutilizar objetos de pacote</span><span class="sxs-lookup"><span data-stu-id="66e0d-102">Reuse of Package Objects</span></span>
  <span data-ttu-id="66e0d-103">Agrupa frequentemente as funcionalidades que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="66e0d-103">Frequently packages functionality that you want to reuse.</span></span> <span data-ttu-id="66e0d-104">Por exemplo, se você criou um conjunto de tarefas, poderá reutilizar os itens juntos como um grupo ou como um único item, como um gerenciador de conexões que você criou em um projeto diferente do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="66e0d-104">For example, if you created a set of tasks, you might want to reuse the items together as a group, or you might want to reuse a single item such as a connection manager that you created in a different [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
## <a name="copy-and-paste"></a><span data-ttu-id="66e0d-105">Copiar e colar</span><span class="sxs-lookup"><span data-stu-id="66e0d-105">Copy and Paste</span></span>  
 <span data-ttu-id="66e0d-106">O [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] e [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer oferecem suporte a copiar e colar objetos de pacote, que podem incluir itens do fluxo de controle, itens do fluxo de dados e gerenciadores de conexões.</span><span class="sxs-lookup"><span data-stu-id="66e0d-106">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer support copying and pasting package objects, which can include control flow items, data flow items, and connection managers.</span></span> <span data-ttu-id="66e0d-107">Você pode copiar e colar entre projetos e entre pacotes.</span><span class="sxs-lookup"><span data-stu-id="66e0d-107">You can copy and paste between projects and between packages.</span></span> <span data-ttu-id="66e0d-108">Se a solução contiver múltiplos projetos, você poderá copiar entre projetos e os projetos podem ser de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="66e0d-108">If the solution contains multiple projects you can copy between projects, and the projects can be of different types.</span></span>  
  
 <span data-ttu-id="66e0d-109">Se uma solução contiver múltiplos pacotes, você poderá copiar e colar entre eles.</span><span class="sxs-lookup"><span data-stu-id="66e0d-109">If a solution contains multiple packages, you can copy and paste between them.</span></span> <span data-ttu-id="66e0d-110">Os pacotes podem estar nos mesmos projetos ou em projetos [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] diferentes.</span><span class="sxs-lookup"><span data-stu-id="66e0d-110">The packages can be in the same or different [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects.</span></span> <span data-ttu-id="66e0d-111">Entretanto, objetos de pacote podem ter dependências em outros objetos, sem os quais eles não são válidos.</span><span class="sxs-lookup"><span data-stu-id="66e0d-111">However, package objects may have dependencies on other objects, without which they are not valid.</span></span> <span data-ttu-id="66e0d-112">Por exemplo, uma tarefa Executar SQL usa um gerenciador de conexões, que você também deve copiar para que a tarefa funcione.</span><span class="sxs-lookup"><span data-stu-id="66e0d-112">For example, an Execute SQL task uses a connection manager, which you must copy as well to make the task work.</span></span> <span data-ttu-id="66e0d-113">Além disso, alguns objetos de pacote exigem que o pacote já contenha um determinado objeto, e sem esse objeto você não pode colar os objetos copiados com sucesso para um pacote.</span><span class="sxs-lookup"><span data-stu-id="66e0d-113">Also, some package objects require that the package already contain a certain object, and without this object you cannot successfully paste the copied objects into a package.</span></span> <span data-ttu-id="66e0d-114">Por exemplo, você não pode colar um fluxo de dados em um pacote que não tenha, no mínimo, uma tarefa de Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="66e0d-114">For example, you cannot paste a data flow into a package that does not have at least one Data Flow task.</span></span>  
  
 <span data-ttu-id="66e0d-115">Você pode descobrir que pode copiar os mesmos pacotes repetidamente.</span><span class="sxs-lookup"><span data-stu-id="66e0d-115">You may find that you copy the same packages repeatedly.</span></span> <span data-ttu-id="66e0d-116">Para evitar o processo de cópia, você pode designar estes pacotes como modelos e usá-los quando criar novos pacotes.</span><span class="sxs-lookup"><span data-stu-id="66e0d-116">To avoid the copy process, you can designate these packages as templates and use them when you create new packages.</span></span>  
  
 <span data-ttu-id="66e0d-117">Quando você copia um objeto de pacote, o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] automaticamente atribui uma nova GUID para a propriedade `ID` do novo objeto e atualiza a propriedade `Name`.</span><span class="sxs-lookup"><span data-stu-id="66e0d-117">When you copy a package object, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] automatically assigns a new GUID to the `ID` property of the new object and updates the `Name` property.</span></span>  
  
 <span data-ttu-id="66e0d-118">Você não pode copiar variáveis.</span><span class="sxs-lookup"><span data-stu-id="66e0d-118">You cannot copy variables.</span></span> <span data-ttu-id="66e0d-119">Se um objeto como uma tarefa usar variáveis, então você deve recriar as variáveis no pacote de destino.</span><span class="sxs-lookup"><span data-stu-id="66e0d-119">If an object such as a task uses variables, then you must re-create the variables in the destination package.</span></span> <span data-ttu-id="66e0d-120">Por outro lado, se você copiar o pacote inteiro, as variáveis no pacote também serão copiadas.</span><span class="sxs-lookup"><span data-stu-id="66e0d-120">In contrast, if you copy the entire package, then the variables in the package are also copied.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="66e0d-121">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="66e0d-121">Related Tasks</span></span>  
  
-   [<span data-ttu-id="66e0d-122">Copiar objetos de pacote</span><span class="sxs-lookup"><span data-stu-id="66e0d-122">Copy Package Objects</span></span>](../../2014/integration-services/copy-package-objects.md)  
  
-   [<span data-ttu-id="66e0d-123">Copiar itens do projeto</span><span class="sxs-lookup"><span data-stu-id="66e0d-123">Copy Project Items</span></span>](../../2014/integration-services/copy-project-items.md)  
  
-   [<span data-ttu-id="66e0d-124">Salvar um pacote como um modelo de pacote</span><span class="sxs-lookup"><span data-stu-id="66e0d-124">Save a Package as a Package Template</span></span>](../../2014/integration-services/save-a-package-as-a-package-template.md)  
  
  
