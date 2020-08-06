---
title: Dependências de objeto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.objectdependencies.f1
ms.assetid: c63d1160-3f3d-45df-99be-6fe081125fb5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13d1775f1e4e6885fe56a43ce40c4ac155c5b361
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685415"
---
# <a name="object-dependencies"></a><span data-ttu-id="ecab4-102">Dependências de objeto</span><span class="sxs-lookup"><span data-stu-id="ecab4-102">Object Dependencies</span></span>
  <span data-ttu-id="ecab4-103">Alguns objetos de banco de dados têm dependências de outros objetos de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ecab4-103">Some database objects have dependencies upon other database objects.</span></span> <span data-ttu-id="ecab4-104">Por exemplo, exibições e procedimentos armazenados dependem da existência de tabelas que contenham dados retornados pela exibição ou pelo procedimento.</span><span class="sxs-lookup"><span data-stu-id="ecab4-104">For example, views and stored procedures depend upon the existence of tables that contain the data returned by the view or procedure.</span></span> <span data-ttu-id="ecab4-105">As **Dependências entre objetos (página Geral)** para o objeto atual lista ambos os objetos de banco de dados que devem estar presentes para o objeto funcionar corretamente e os objetos que dependem do objeto selecionado.</span><span class="sxs-lookup"><span data-stu-id="ecab4-105">The **Object Dependencies (General Page)** for the current object lists both the database objects that must be present for the object to function properly and the objects that depend upon the selected object.</span></span> <span data-ttu-id="ecab4-106">Um objeto que faz referência a outro objeto em sua definição, e essa definição é armazenada no catálogo do sistema, é denominado *entidade de referência*.</span><span class="sxs-lookup"><span data-stu-id="ecab4-106">An object that references another object in its definition and that definition is stored in the system catalog is called a *referencing entity*.</span></span> <span data-ttu-id="ecab4-107">Um objeto que é referenciado por outro objeto é denominado *entidade referenciada*.</span><span class="sxs-lookup"><span data-stu-id="ecab4-107">An object that is referred to by another object is called a *referenced entity*.</span></span>  
  
 <span data-ttu-id="ecab4-108">As **Dependências entre objetos (página Avançado)** do objeto atual lista os objetos de banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e os objetos do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que dependem do objeto.</span><span class="sxs-lookup"><span data-stu-id="ecab4-108">The **Object Dependencies (Advanced Page)** for the current object lists the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database objects and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] objects that depend on the object.</span></span> <span data-ttu-id="ecab4-109">Os objetos podem ser armazenados em servidores diferentes.</span><span class="sxs-lookup"><span data-stu-id="ecab4-109">The objects may be stored on different servers.</span></span>  
  
 <span data-ttu-id="ecab4-110">Use esta caixa de diálogo para entender as dependências antes de alterar ou excluir o objeto selecionado.</span><span class="sxs-lookup"><span data-stu-id="ecab4-110">Use this dialog box to understand the dependencies before changing or deleting the selected object.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="ecab4-111">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="ecab4-111">UI element list</span></span>  
 <span data-ttu-id="ecab4-112">**Objetos que dependem de**  _\<selected object>_</span><span class="sxs-lookup"><span data-stu-id="ecab4-112">**Objects that depend on**  _\<selected object>_</span></span>  
 <span data-ttu-id="ecab4-113">Clicando neste botão, você exibe uma lista dos objetos que são rastreados por dependência e que dependem do objeto selecionado.</span><span class="sxs-lookup"><span data-stu-id="ecab4-113">Clicking this button displays a list of those objects that are dependency-tracked and that depend on the selected object.</span></span>  
  
 <span data-ttu-id="ecab4-114">**Objetos nos quais** _\<selected object>_ **depende**    </span><span class="sxs-lookup"><span data-stu-id="ecab4-114">**Objects on which**  _\<selected object>_  **depends**</span></span>  
 <span data-ttu-id="ecab4-115">Clicando neste botão, você exibe uma lista dos objetos que são rastreados por dependência e dos quais depende o objeto selecionado.</span><span class="sxs-lookup"><span data-stu-id="ecab4-115">Clicking this button displays a list of those objects that are dependency-tracked, on which the selected object depends.</span></span>  
  
 <span data-ttu-id="ecab4-116">**Dependências**</span><span class="sxs-lookup"><span data-stu-id="ecab4-116">**Dependencies**</span></span>  
 <span data-ttu-id="ecab4-117">Se você clicar em **Objetos que dependem de** _\<selected object>_ , será exibida uma exibição hierárquica dos objetos que dependem do objeto selecionado.</span><span class="sxs-lookup"><span data-stu-id="ecab4-117">If **Objects that depend on** _\<selected object>_ is clicked, this displays an hierarchical view of objects that depend on the selected object.</span></span> <span data-ttu-id="ecab4-118">Se **Objetos dos quais** _\<selected object>_ **depende** for clicado, será exibida uma exibição hierárquica dos objetos dos quais o objeto selecionado depende.</span><span class="sxs-lookup"><span data-stu-id="ecab4-118">If **Objects on which** _\<selected object>_ **depends** is clicked, this displays an hierarchical view of objects on which the selected object depends.</span></span>  
  
 <span data-ttu-id="ecab4-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ecab4-119">**Name**</span></span>  
 <span data-ttu-id="ecab4-120">Exibe o nome do objeto selecionado no modo de exibição de árvore **Dependências** acima.</span><span class="sxs-lookup"><span data-stu-id="ecab4-120">Displays the name of the object selected in the **Dependencies** tree view above.</span></span>  
  
 <span data-ttu-id="ecab4-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ecab4-121">**Type**</span></span>  
 <span data-ttu-id="ecab4-122">Exibe o tipo do objeto selecionado no modo de exibição de árvore **Dependências** acima.</span><span class="sxs-lookup"><span data-stu-id="ecab4-122">Displays the type of the object selected in the **Dependencies** tree view above.</span></span>  
  
 <span data-ttu-id="ecab4-123">**Hora da Última Sincronização**</span><span class="sxs-lookup"><span data-stu-id="ecab4-123">**Last Sync Time**</span></span>  
 > [!NOTE]  
>  <span data-ttu-id="ecab4-124">Esta opção só está disponível na página **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="ecab4-124">This option is available only on the **Advanced** page.</span></span>  
  
 <span data-ttu-id="ecab4-125">Especifica a data e a hora em que as informações de dependência foram atualizadas pela última vez.</span><span class="sxs-lookup"><span data-stu-id="ecab4-125">Specifies the time and date when the dependency information was last updated.</span></span>  
  
 <span data-ttu-id="ecab4-126">**Tipo de dependência**</span><span class="sxs-lookup"><span data-stu-id="ecab4-126">**Dependency type**</span></span>  
 > [!NOTE]  
>  <span data-ttu-id="ecab4-127">Esta opção só está disponível na página **Geral** .</span><span class="sxs-lookup"><span data-stu-id="ecab4-127">This option is available only on the **General** page.</span></span>  
  
 <span data-ttu-id="ecab4-128">Exibe o tipo de dependência entre dois objetos.</span><span class="sxs-lookup"><span data-stu-id="ecab4-128">Displays the type of dependency between two objects.</span></span> <span data-ttu-id="ecab4-129">Um dos seguintes pode ser feito:</span><span class="sxs-lookup"><span data-stu-id="ecab4-129">Can be one of the following:</span></span>  
  
-   <span data-ttu-id="ecab4-130">Dependência associada a esquema</span><span class="sxs-lookup"><span data-stu-id="ecab4-130">Schema-bound dependency</span></span>  
  
     <span data-ttu-id="ecab4-131">É uma relação entre dois objetos que impedem o objeto mencionado de ser descartado ou modificado desde que exista o objeto referenciado.</span><span class="sxs-lookup"><span data-stu-id="ecab4-131">Is a relationship between two objects that prevents the referenced object from being dropped or modified as long as the referencing object exists.</span></span> <span data-ttu-id="ecab4-132">Uma dependência associada a esquema é criada quando uma exibição ou função definida pelo usuário é criada usando a cláusula WITH SCHEMABINDING, ou quando uma tabela faz referência a outro objeto por uma restrição CHECK ou DEFAULT ou na definição de uma coluna computada.</span><span class="sxs-lookup"><span data-stu-id="ecab4-132">A schema-bound dependency is created when a view or user-defined function is created by using the WITH SCHEMABINDING clause, or when a table references another object through a CHECK or DEFAULT constraint or in the definition of a computed column.</span></span>  
  
-   <span data-ttu-id="ecab4-133">Dependência não associada a esquema</span><span class="sxs-lookup"><span data-stu-id="ecab4-133">Non-schema-bound dependency</span></span>  
  
     <span data-ttu-id="ecab4-134">É uma relação entre dois objetos que não impedem o descarte ou a modificação do objeto referenciado.</span><span class="sxs-lookup"><span data-stu-id="ecab4-134">Is a relationship between two objects that does not prevent the referenced object from being dropped or modified.</span></span>  
  
-   <span data-ttu-id="ecab4-135">Entidade não disponível ou não resolvida</span><span class="sxs-lookup"><span data-stu-id="ecab4-135">Not available or Unresolved Entity</span></span>  
  
     <span data-ttu-id="ecab4-136">Indica que o tipo de dependência não pode ser determinado.</span><span class="sxs-lookup"><span data-stu-id="ecab4-136">Indicates the dependency type cannot be determined.</span></span> <span data-ttu-id="ecab4-137">Isso só acontece quando o objeto selecionado estiver em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que é anterior a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecab4-137">This occurs only when the selected object is on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
  
