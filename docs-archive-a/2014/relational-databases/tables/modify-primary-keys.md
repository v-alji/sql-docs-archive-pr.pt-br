---
title: Modificar chaves primárias | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying primary keys
- primary keys [SQL Server], modifying
ms.assetid: 8e2a15ba-1cd1-4408-b860-16c3ee37d635
author: stevestein
ms.author: sstein
ms.openlocfilehash: f24deeac45491f9097d90ee0407464f928a0713b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568397"
---
# <a name="modify-primary-keys"></a><span data-ttu-id="c7f64-102">Modificar chaves primárias</span><span class="sxs-lookup"><span data-stu-id="c7f64-102">Modify Primary Keys</span></span>
  <span data-ttu-id="c7f64-103">Você pode modificar uma chave primária no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7f64-103">You can modify a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c7f64-104">Você pode modificar a chave primária de uma tabela alterando a ordem das colunas, o nome do índice, a opção clusterizada ou o fator de preenchimento.</span><span class="sxs-lookup"><span data-stu-id="c7f64-104">You can modify the primary key of a table by changing the column order, index name, clustered option, or fill factor.</span></span>  
  
 <span data-ttu-id="c7f64-105">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="c7f64-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c7f64-106">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="c7f64-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c7f64-107">Segurança</span><span class="sxs-lookup"><span data-stu-id="c7f64-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c7f64-108">**Para modificar uma chave primária usando:**</span><span class="sxs-lookup"><span data-stu-id="c7f64-108">**To modify a primary key, using:**</span></span>  
  
     [<span data-ttu-id="c7f64-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c7f64-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c7f64-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c7f64-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c7f64-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c7f64-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c7f64-112">Segurança</span><span class="sxs-lookup"><span data-stu-id="c7f64-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c7f64-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="c7f64-113">Permissions</span></span>  
 <span data-ttu-id="c7f64-114">Exige a permissão ALTER na tabela.</span><span class="sxs-lookup"><span data-stu-id="c7f64-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c7f64-115">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c7f64-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-primary-key"></a><span data-ttu-id="c7f64-116">Para modificar uma chave primária</span><span class="sxs-lookup"><span data-stu-id="c7f64-116">To modify a primary key</span></span>  
  
1.  <span data-ttu-id="c7f64-117">Abra o Designer de Tabela da tabela cuja chave primária você quer modificar, clique com o botão direito do mouse no Designer de Tabela e escolha **Índices/Chaves** no menu de atalho.</span><span class="sxs-lookup"><span data-stu-id="c7f64-117">Open the Table Designer for the table whose primary key you want to modify, right-click in the Table Designer, and choose **Indexes/Keys** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="c7f64-118">Na caixa de diálogo **Índices/Chaves** , selecione o índice de chave primária na lista **Índice ou Chave Exclusiva/Primária Selecionada** .</span><span class="sxs-lookup"><span data-stu-id="c7f64-118">In the **Indexes/Keys** dialog box, select the primary key index from the **Selected Primary/Unique Key or Index** list.</span></span>  
  
3.  <span data-ttu-id="c7f64-119">Complete uma ação da seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="c7f64-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="c7f64-120">Para</span><span class="sxs-lookup"><span data-stu-id="c7f64-120">To</span></span>|<span data-ttu-id="c7f64-121">Siga estas etapas</span><span class="sxs-lookup"><span data-stu-id="c7f64-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="c7f64-122">Renomeie a chave primária</span><span class="sxs-lookup"><span data-stu-id="c7f64-122">Rename the primary key</span></span>|<span data-ttu-id="c7f64-123">Digite um novo nome na caixa **Nome** .</span><span class="sxs-lookup"><span data-stu-id="c7f64-123">Type a new name in the **Name** box.</span></span> <span data-ttu-id="c7f64-124">Verifique se seu novo nome não duplica um nome na lista **Índice ou Chave Exclusiva/Primária Selecionada** .</span><span class="sxs-lookup"><span data-stu-id="c7f64-124">Make sure that your new name does not duplicate a name in the **Selected Primary/Unique Key or Index** list.</span></span>|  
    |<span data-ttu-id="c7f64-125">Definir a opção clustered</span><span class="sxs-lookup"><span data-stu-id="c7f64-125">Set the clustered option</span></span>|<span data-ttu-id="c7f64-126">Para criar um índice clusterizado para a chave primária, selecione **Criar como CLUSTERED**e selecione a opção na caixa de listagem suspensa.</span><span class="sxs-lookup"><span data-stu-id="c7f64-126">To create a clustered index for the primary key, select **Create as CLUSTERED**, and select the option from the drop-down list box.</span></span> <span data-ttu-id="c7f64-127">Só pode existir um índice clusterizado por tabela.</span><span class="sxs-lookup"><span data-stu-id="c7f64-127">Only one clustered index can exist per table.</span></span> <span data-ttu-id="c7f64-128">Se essa opção não estiver disponível para seu índice, você deve desmarcar essa configuração no primeiro índice clusterizado existente.</span><span class="sxs-lookup"><span data-stu-id="c7f64-128">If this option is not available for your index, you must first clear this setting on the existing clustered index.</span></span><br /><br /> <span data-ttu-id="c7f64-129">Se essa opção não for selecionada, um índice exclusivo não clusterizado será criado.</span><span class="sxs-lookup"><span data-stu-id="c7f64-129">If this option is not selected, a unique nonclustered index is created.</span></span>|  
    |<span data-ttu-id="c7f64-130">Definir um fator de preenchimento</span><span class="sxs-lookup"><span data-stu-id="c7f64-130">Define a fill factor</span></span>|<span data-ttu-id="c7f64-131">Expanda a categoria **Especificação de Preenchimento** e digite um inteiro de 0 a 100 na caixa **Fator de Preenchimento** .</span><span class="sxs-lookup"><span data-stu-id="c7f64-131">Expand the **Fill Specification** category and type an integer from 0 to 100 in the **Fill factor** box.</span></span> <span data-ttu-id="c7f64-132">Para obter mais informações sobre fatores de preenchimento e seus usos, veja [Especificar fator de preenchimento para um índice](../indexes/specify-fill-factor-for-an-index.md).</span><span class="sxs-lookup"><span data-stu-id="c7f64-132">For more information about fill factors and their uses, see [Specify Fill Factor for an Index](../indexes/specify-fill-factor-for-an-index.md).</span></span>|  
    |<span data-ttu-id="c7f64-133">Altere a ordem da coluna</span><span class="sxs-lookup"><span data-stu-id="c7f64-133">Change the column order</span></span>|<span data-ttu-id="c7f64-134">Selecione **Colunas** e clique nas reticências **(...)** à direita da propriedade.</span><span class="sxs-lookup"><span data-stu-id="c7f64-134">Select **Columns**, and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="c7f64-135">Na caixa de diálogo  **Colunas de Índices** , remova as colunas da chave primária.</span><span class="sxs-lookup"><span data-stu-id="c7f64-135">In the  **Index Columns** dialog box, remove the columns from the primary key.</span></span> <span data-ttu-id="c7f64-136">Depois, adicione as colunas de novo na ordem desejada.</span><span class="sxs-lookup"><span data-stu-id="c7f64-136">Then add the columns back in the order you want.</span></span> <span data-ttu-id="c7f64-137">Para remover uma coluna da chave, simplesmente remova o nome de coluna da lista de nomes **Coluna** .</span><span class="sxs-lookup"><span data-stu-id="c7f64-137">To remove a column from the key, simply remove the column name from the **Column** name list.</span></span>|  
  
4.  <span data-ttu-id="c7f64-138">No menu **Arquivo**, clique em **Salvar**_nome da tabela_.</span><span class="sxs-lookup"><span data-stu-id="c7f64-138">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c7f64-139">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c7f64-139">Using Transact-SQL</span></span>  
 <span data-ttu-id="c7f64-140">**Para modificar uma chave primária**</span><span class="sxs-lookup"><span data-stu-id="c7f64-140">**To modify a primary key**</span></span>  
  
 <span data-ttu-id="c7f64-141">Para modificar uma restrição PRIMARY KEY usando o Transact-SQL, exclua primeiramente a PRIMARY KEY já existente e, em seguida, recrie essa restrição com a nova definição.</span><span class="sxs-lookup"><span data-stu-id="c7f64-141">To modify a PRIMARY KEY constraint using Transact-SQL, you must first delete the existing PRIMARY KEY constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="c7f64-142">Para obter mais informações, consulte [Delete Primary Keys](delete-primary-keys.md) e [Create Primary Keys](create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="c7f64-142">For more information, see [Delete Primary Keys](delete-primary-keys.md) and [Create Primary Keys](create-primary-keys.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
