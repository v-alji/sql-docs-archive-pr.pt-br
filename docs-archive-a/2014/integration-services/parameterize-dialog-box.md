---
title: Caixa de diálogo Parametrizar | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.parameter.f1
ms.assetid: fac02b6d-d247-447a-8940-e8700c7ac350
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8db19844132402740aec092d6e88f3c9e3864d58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574086"
---
# <a name="parameterize-dialog-box"></a><span data-ttu-id="359ac-102">Parameterize Dialog Box</span><span class="sxs-lookup"><span data-stu-id="359ac-102">Parameterize Dialog Box</span></span>
  <span data-ttu-id="359ac-103">A caixa de diálogo **Parametrizar** permite que você associe um novo parâmetro ou um existente à propriedade de uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="359ac-103">The **Parameterize** dialog box enables you to associate a new or an existing parameter with a property of a task.</span></span> <span data-ttu-id="359ac-104">Você abre a caixa de diálogo clicando com o botão direito em uma tarefa ou na guia Fluxo de Controle no Designer do [!INCLUDE[ssIS](../includes/ssis-md.md)] e, em seguida, clique em **Parametrizar**.</span><span class="sxs-lookup"><span data-stu-id="359ac-104">You open the dialog box by right-clicking a task or the Control Flow tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer and then by clicking **Parameterize**.</span></span> <span data-ttu-id="359ac-105">A lista a seguir descreve os elementos da interface de usuário na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="359ac-105">The following list describes UI elements in the dialog box.</span></span> <span data-ttu-id="359ac-106">Para obter mais informações sobre parâmetros, consulte [Parâmetros do Integration Services &#40;SSIS&#41;](integration-services-ssis-package-and-project-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="359ac-106">For more information about parameters, see [Integration Services &#40;SSIS&#41; Parameters](integration-services-ssis-package-and-project-parameters.md).</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="359ac-107">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="359ac-107">UI element list</span></span>  
 <span data-ttu-id="359ac-108">**Propriedade**</span><span class="sxs-lookup"><span data-stu-id="359ac-108">**Property**</span></span>  
 <span data-ttu-id="359ac-109">Selecione a propriedade da tarefa que você deseja associar a um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="359ac-109">Select the property of the task that you want to associate with a parameter.</span></span> <span data-ttu-id="359ac-110">Esta lista é preenchida com todas as propriedades que podem ser parametrizadas.</span><span class="sxs-lookup"><span data-stu-id="359ac-110">This list is populated with all the properties that can be parameterized.</span></span>  
  
 <span data-ttu-id="359ac-111">**Usar parâmetros existentes**</span><span class="sxs-lookup"><span data-stu-id="359ac-111">**Use existing parameter**</span></span>  
 <span data-ttu-id="359ac-112">Selecione esta opção para associar a propriedade da tarefa a um parâmetro existente e, em seguida, selecione o parâmetro na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="359ac-112">Select this option to associate the property of task with an existing parameter and then select the parameter from drop-down list.</span></span>  
  
 <span data-ttu-id="359ac-113">**Não usar parâmetro**</span><span class="sxs-lookup"><span data-stu-id="359ac-113">**Do not use parameter**</span></span>  
 <span data-ttu-id="359ac-114">Selecione esta opção para remover uma referência a um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="359ac-114">Select this option to remove a reference to a parameter.</span></span> <span data-ttu-id="359ac-115">O parâmetro não é excluído.</span><span class="sxs-lookup"><span data-stu-id="359ac-115">The parameter is not deleted.</span></span>  
  
 <span data-ttu-id="359ac-116">**Criar novo parâmetro**</span><span class="sxs-lookup"><span data-stu-id="359ac-116">**Create new parameter**</span></span>  
 <span data-ttu-id="359ac-117">Selecione esta opção para criar um novo parâmetro que você deseja associar à propriedade da tarefa.</span><span class="sxs-lookup"><span data-stu-id="359ac-117">Select this option to create a new parameter that you want to associate with the property of the task.</span></span>  
  
 <span data-ttu-id="359ac-118">**Nome**</span><span class="sxs-lookup"><span data-stu-id="359ac-118">**Name**</span></span>  
 <span data-ttu-id="359ac-119">Especifica o nome do parâmetro que você quer criar.</span><span class="sxs-lookup"><span data-stu-id="359ac-119">Specify the name of the parameter you want to create.</span></span>  
  
 <span data-ttu-id="359ac-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="359ac-120">**Description**</span></span>  
 <span data-ttu-id="359ac-121">Especifique a descrição para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="359ac-121">Specify the description for parameter.</span></span>  
  
 <span data-ttu-id="359ac-122">**Valor**</span><span class="sxs-lookup"><span data-stu-id="359ac-122">**Value**</span></span>  
 <span data-ttu-id="359ac-123">Especifique o valor padrão para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="359ac-123">Specify the default value for the parameter.</span></span> <span data-ttu-id="359ac-124">Isto também é conhecido como o padrão de design que pode ser substituído posteriormente no momento da implantação.</span><span class="sxs-lookup"><span data-stu-id="359ac-124">This is also known as the design default, which can be overridden later at the deployment time.</span></span>  
  
 <span data-ttu-id="359ac-125">**Escopo**</span><span class="sxs-lookup"><span data-stu-id="359ac-125">**Scope**</span></span>  
 <span data-ttu-id="359ac-126">Especifique o escopo do parâmetro selecionando a opção **Projeto** ou **Pacote** .</span><span class="sxs-lookup"><span data-stu-id="359ac-126">Specify the scope of the parameter by selecting either **Project** or **Package** option.</span></span> <span data-ttu-id="359ac-127">Os parâmetros do projeto são usados para fornecer uma entrada externa que o projeto recebe para um ou mais pacotes no projeto.</span><span class="sxs-lookup"><span data-stu-id="359ac-127">Project parameters are used to supply any external input the project receives to one or more packages in the project.</span></span> <span data-ttu-id="359ac-128">Os parâmetros do pacote permitem modificar a execução do pacote sem a necessidade de editar e reimplantar o pacote.</span><span class="sxs-lookup"><span data-stu-id="359ac-128">Package parameters allow you to modify package execution without having to edit and redeploy the package.</span></span>  
  
 <span data-ttu-id="359ac-129">**Diferencia**</span><span class="sxs-lookup"><span data-stu-id="359ac-129">**Sensitive**</span></span>  
 <span data-ttu-id="359ac-130">Especifique se o parâmetro é confidencial marcando ou desmarcando a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="359ac-130">Specify whether the parameter is a sensitive by checking or clearing the check box.</span></span> <span data-ttu-id="359ac-131">Valores de parâmetros confidenciais são criptografados no catálogo e aparecem como um valor NULL quando exibidos com o Transact-SQL ou o SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="359ac-131">Sensitive parameter values are encrypted in the catalog and appear as a NULL value when viewed with Transact-SQL or SQL Server Management Studio.</span></span>  
  
 <span data-ttu-id="359ac-132">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="359ac-132">**Required**</span></span>  
 <span data-ttu-id="359ac-133">Especifique se o parâmetro exige que um valor diferente do padrão de design seja especificado para que o pacote possa ser executado.</span><span class="sxs-lookup"><span data-stu-id="359ac-133">Specify whether the parameter requires that a value, other than the design default, is specified before the package can execute.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="359ac-134">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="359ac-134">UI element list</span></span>  
  
