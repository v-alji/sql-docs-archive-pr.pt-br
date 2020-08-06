---
title: Opções (designers – página designers de tabela e banco de dados) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Designers.Table_Designer
ms.assetid: b43f4b97-17b9-4004-a824-f77b9e145741
author: stevestein
ms.author: sstein
ms.openlocfilehash: d8a1218b4ea1ae9c6f9cf734bb33a2a4bebcb167
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576106"
---
# <a name="options-designers-table-and-database-designers-page"></a><span data-ttu-id="6c7ff-102">Opções (designers – página designers de tabela e banco de dados)</span><span class="sxs-lookup"><span data-stu-id="6c7ff-102">Options (Designers-Table and Database Designers Page)</span></span>
  <span data-ttu-id="6c7ff-103">Use esta página para determinar o comportamento padrão do designer.</span><span class="sxs-lookup"><span data-stu-id="6c7ff-103">Use this page to determine the default behavior of the designer.</span></span> <span data-ttu-id="6c7ff-104">Para acessar as configurações, no menu **Ferramentas** , clique em **Opções**, expanda  a pasta **Designers** e clique em **Designer de Tabela**.</span><span class="sxs-lookup"><span data-stu-id="6c7ff-104">To access the settings, on the **Tools** menu, click **Options**, expand the **Designers** folder, and click **Table Designer**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="6c7ff-105">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="6c7ff-105">UI element list</span></span>  
 <span data-ttu-id="6c7ff-106">**Substituir valor de tempo limite da cadeia de caracteres da conexão para atualizações do designer de tabela**</span><span class="sxs-lookup"><span data-stu-id="6c7ff-106">**Override connection string time-out value for table designer updates**</span></span>  
 <span data-ttu-id="6c7ff-107">Permite que um novo valor de tempo limite seja definido para ações no designer de tabela.</span><span class="sxs-lookup"><span data-stu-id="6c7ff-107">Permits a new time-out value to be set for the actions of the table designer.</span></span> <span data-ttu-id="6c7ff-108">Isso pode ser útil quando o designer de tabela afetar uma tabela grande e requerer tempo extra para concluir a modificação da tabela.</span><span class="sxs-lookup"><span data-stu-id="6c7ff-108">This can be useful when the table designer affects a large table and requires extra time to complete the table modification.</span></span>  
  
 <span data-ttu-id="6c7ff-109">**Tempo limite de transação após**</span><span class="sxs-lookup"><span data-stu-id="6c7ff-109">**Transaction time-out after**</span></span>  
 <span data-ttu-id="6c7ff-110">Define um valor de tempo limite para o designer de tabela.</span><span class="sxs-lookup"><span data-stu-id="6c7ff-110">Sets a time-out value for the table designer.</span></span>  
  
 <span data-ttu-id="6c7ff-111">**Gerar scripts de alteração automaticamente**</span><span class="sxs-lookup"><span data-stu-id="6c7ff-111">**Auto generate change scripts**</span></span>  
 <span data-ttu-id="6c7ff-112">Cria, automaticamente, um script para implementar as alterações definidas no designer de tabela.</span><span class="sxs-lookup"><span data-stu-id="6c7ff-112">Automatically creates a script to implement the changes defined in the table designer.</span></span>  
  
 <span data-ttu-id="6c7ff-113">**Avisar sobre chaves primárias nulas**</span><span class="sxs-lookup"><span data-stu-id="6c7ff-113">**Warn on null primary keys**</span></span>  
 <span data-ttu-id="6c7ff-114">Fornece uma caixa de diálogo de aviso quando um campo que é selecionado para uma chave primária puder conter valores nulos.</span><span class="sxs-lookup"><span data-stu-id="6c7ff-114">Provides a warning dialog box when a field that is selected for a primary key can contain null values.</span></span>  
  
 <span data-ttu-id="6c7ff-115">**Aviso sobre detecção de diferença**</span><span class="sxs-lookup"><span data-stu-id="6c7ff-115">**Warn about difference detection**</span></span>  
 <span data-ttu-id="6c7ff-116">Se você selecionar esta caixa, uma caixa de mensagens listará qualquer conflito entre suas alterações e as feitas por outro usuário ao salvar alterações.</span><span class="sxs-lookup"><span data-stu-id="6c7ff-116">If you check this box, when you save the changes, a message box will list any conflicts between your changes and changes that were made by another user.</span></span>  
  
 <span data-ttu-id="6c7ff-117">**Avisar sobre tabelas afetadas**</span><span class="sxs-lookup"><span data-stu-id="6c7ff-117">**Warn about tables affected**</span></span>  
 <span data-ttu-id="6c7ff-118">Fornece uma caixa de diálogo de aviso que lista as tabelas que serão afetadas pela ação e solicita confirmação.</span><span class="sxs-lookup"><span data-stu-id="6c7ff-118">Provides a warning dialog box that lists the tables to be affected by the action and prompts for confirmation.</span></span>  
  
 <span data-ttu-id="6c7ff-119">**Evitar salvar alterações que exijam recriação de tabela**</span><span class="sxs-lookup"><span data-stu-id="6c7ff-119">**Prevent saving changes that require table re-creation**</span></span>  
 <span data-ttu-id="6c7ff-120">Impede um usuário de fazer alterações que requerem recriação de tabela.</span><span class="sxs-lookup"><span data-stu-id="6c7ff-120">Prevents a user from making changes that require re-creating the table.</span></span> <span data-ttu-id="6c7ff-121">As ações seguintes poderiam exigir a recriação de uma tabela:</span><span class="sxs-lookup"><span data-stu-id="6c7ff-121">The following actions might require a table to be re-created:</span></span>  
  
-   <span data-ttu-id="6c7ff-122">Adição de uma nova coluna no meio da tabela</span><span class="sxs-lookup"><span data-stu-id="6c7ff-122">Adding a new column to the middle of the table</span></span>  
  
-   <span data-ttu-id="6c7ff-123">Descarte de uma coluna</span><span class="sxs-lookup"><span data-stu-id="6c7ff-123">Dropping a column</span></span>  
  
-   <span data-ttu-id="6c7ff-124">Alteração da nulidade da coluna</span><span class="sxs-lookup"><span data-stu-id="6c7ff-124">Changing column nullability</span></span>  
  
-   <span data-ttu-id="6c7ff-125">Alteração da ordem das colunas</span><span class="sxs-lookup"><span data-stu-id="6c7ff-125">Changing the order of the columns</span></span>  
  
-   <span data-ttu-id="6c7ff-126">Alteração do tipo de dados de uma coluna</span><span class="sxs-lookup"><span data-stu-id="6c7ff-126">Changing the data type of a column</span></span>  
  
 <span data-ttu-id="6c7ff-127">**Exibição de tabela padrão**</span><span class="sxs-lookup"><span data-stu-id="6c7ff-127">**Default table view**</span></span>  
 <span data-ttu-id="6c7ff-128">Selecione o modo que você deseja ver tabelas no designer:</span><span class="sxs-lookup"><span data-stu-id="6c7ff-128">Select the way you want to see tables in the designers:</span></span>  
  
-   <span data-ttu-id="6c7ff-129">**Standard**</span><span class="sxs-lookup"><span data-stu-id="6c7ff-129">**Standard**</span></span>  
  
     <span data-ttu-id="6c7ff-130">Mostra o cabeçalho, todos os nomes das colunas, os tipos de dados e a configuração Permitir Nulos da tabela.</span><span class="sxs-lookup"><span data-stu-id="6c7ff-130">Shows the table header, all column names, data types, and the Allow Nulls setting.</span></span>  
  
-   <span data-ttu-id="6c7ff-131">**Nomes de coluna**</span><span class="sxs-lookup"><span data-stu-id="6c7ff-131">**Column Names**</span></span>  
  
     <span data-ttu-id="6c7ff-132">Mostra os nomes das colunas.</span><span class="sxs-lookup"><span data-stu-id="6c7ff-132">Shows the column names.</span></span>  
  
-   <span data-ttu-id="6c7ff-133">**Chave**</span><span class="sxs-lookup"><span data-stu-id="6c7ff-133">**Key**</span></span>  
  
     <span data-ttu-id="6c7ff-134">Mostra o cabeçalho de tabela e as colunas de chave primária.</span><span class="sxs-lookup"><span data-stu-id="6c7ff-134">Shows the table header and the primary key columns.</span></span>  
  
-   <span data-ttu-id="6c7ff-135">**Apenas nome**</span><span class="sxs-lookup"><span data-stu-id="6c7ff-135">**Name Only**</span></span>  
  
     <span data-ttu-id="6c7ff-136">Mostra apenas o cabeçalho da tabela com seu nome.</span><span class="sxs-lookup"><span data-stu-id="6c7ff-136">Shows only the table header with it's name.</span></span>  
  
-   <span data-ttu-id="6c7ff-137">**Custom**</span><span class="sxs-lookup"><span data-stu-id="6c7ff-137">**Custom**</span></span>  
  
     <span data-ttu-id="6c7ff-138">Permite que você escolha quais colunas deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="6c7ff-138">Allows you to choose which columns to view.</span></span>  
  
 <span data-ttu-id="6c7ff-139">**Iniciar diálogo de adição de tabela no novo diagrama**</span><span class="sxs-lookup"><span data-stu-id="6c7ff-139">**Launch add table dialog on new diagram**</span></span>  
 <span data-ttu-id="6c7ff-140">Abre automaticamente a caixa de diálogo **Adicionar Tabela** quando os designers são abertos.</span><span class="sxs-lookup"><span data-stu-id="6c7ff-140">Automatically opens the **Add Table** dialog box when the designers open.</span></span>  
  
  
