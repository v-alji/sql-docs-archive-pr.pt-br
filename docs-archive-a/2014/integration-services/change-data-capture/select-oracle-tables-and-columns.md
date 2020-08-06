---
title: Selecionar tabelas e colunas Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- selTabCol
ms.assetid: bf73f80e-a954-4c5f-874e-17fdd4082715
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d51e597f1210643b1543ed981045ade7b2fc2b62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572132"
---
# <a name="select-oracle-tables-and-columns"></a><span data-ttu-id="2fee9-102">Selecionar tabelas e colunas Oracle</span><span class="sxs-lookup"><span data-stu-id="2fee9-102">Select Oracle Tables and Columns</span></span>
  <span data-ttu-id="2fee9-103">Use a página Selecione tabelas e colunas Oracle para selecionar as tabelas do banco de dados de origem Oracle onde as alterações são capturadas.</span><span class="sxs-lookup"><span data-stu-id="2fee9-103">Use the Select Oracle Tables and Columns page to select the tables from the Oracle source database where changes are captured.</span></span> <span data-ttu-id="2fee9-104">Esta página tem os seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="2fee9-104">This page has the following elements:</span></span>  
  
## <a name="options"></a><span data-ttu-id="2fee9-105">Opções</span><span class="sxs-lookup"><span data-stu-id="2fee9-105">Options</span></span>  
 <span data-ttu-id="2fee9-106">**Lista Tabela**</span><span class="sxs-lookup"><span data-stu-id="2fee9-106">**Table list**</span></span>  
 <span data-ttu-id="2fee9-107">A lista de tabelas tem três colunas:</span><span class="sxs-lookup"><span data-stu-id="2fee9-107">The table list has three columns:</span></span>  
  
-   <span data-ttu-id="2fee9-108">**Nome da tabela Oracle**: o nome da tabela, incluindo esquema de tabela.</span><span class="sxs-lookup"><span data-stu-id="2fee9-108">**Oracle Table Name**: The name of the table, including the table schema.</span></span>  
  
-   <span data-ttu-id="2fee9-109">**Instância de Captura**: é o nome da instância de captura usada para nomear objetos do Change Data Capture específicos.</span><span class="sxs-lookup"><span data-stu-id="2fee9-109">**Capture Instance**: The name of the capture instance used to name instance-specific change data capture objects.</span></span> <span data-ttu-id="2fee9-110">A instância de captura não pode ser NULL.</span><span class="sxs-lookup"><span data-stu-id="2fee9-110">The capture instance cannot be NULL.</span></span>  
  
     <span data-ttu-id="2fee9-111">Se não for especificado, o nome será derivado do nome do esquema de origem mais o nome da tabela de origem, no formato `<schema-name>_<table-name>`.</span><span class="sxs-lookup"><span data-stu-id="2fee9-111">If not specified, the name is derived from the source schema name plus the source table name in the format `<schema-name>_<table-name>`.</span></span> <span data-ttu-id="2fee9-112">O nome da instância de captura não pode exceder 100 caracteres e deve ser exclusivo no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2fee9-112">The capture instance name cannot exceed 100 characters and must be unique within the database.</span></span>  
  
     <span data-ttu-id="2fee9-113">Você pode clicar em qualquer célula nesta coluna para editar manualmente **capture_instance**.</span><span class="sxs-lookup"><span data-stu-id="2fee9-113">You can click in any cell in this column to manually edit the **capture_instance**.</span></span>  
  
-   <span data-ttu-id="2fee9-114">**Security Role**: o nome da função de banco de dados de associação usada para controlar o acesso aos dados de alteração.</span><span class="sxs-lookup"><span data-stu-id="2fee9-114">**Security Role**: The name of the database gating role used to control access to change data.</span></span>  
  
     <span data-ttu-id="2fee9-115">Você pode clicar em qualquer célula nesta coluna para editar manualmente **security_role**.</span><span class="sxs-lookup"><span data-stu-id="2fee9-115">You can click in any cell in this column to manually edit the **security_role**.</span></span>  
  
 <span data-ttu-id="2fee9-116">**Adicionar tabelas**</span><span class="sxs-lookup"><span data-stu-id="2fee9-116">**Add Tables**</span></span>  
 <span data-ttu-id="2fee9-117">Clique em **Adicionar Tabelas** para abrir a caixa de diálogo Seleção de Tabela em que você pode [Selecionar as tabelas Oracle para capturar alterações](select-oracle-tables-for-capturing-changes.md).</span><span class="sxs-lookup"><span data-stu-id="2fee9-117">Click **Add Tables** to open the Table Selection dialog box where you can [Select Oracle Tables for Capturing Changes](select-oracle-tables-for-capturing-changes.md).</span></span>  
  
 <span data-ttu-id="2fee9-118">**Editar**</span><span class="sxs-lookup"><span data-stu-id="2fee9-118">**Edit**</span></span>  
 <span data-ttu-id="2fee9-119">Selecione uma tabela da lista e selecione **Editar** para abrir a caixa de diálogo **Propriedades** para a tabela em que você pode [Fazer alterações nas tabelas selecionadas para capturar alterações](make-changes-to-the-tables-selected-for-capturing-changes.md).</span><span class="sxs-lookup"><span data-stu-id="2fee9-119">Select a table from the list and select **Edit** to open the **Properties** dialog box for that table where you can [Make Changes to the Tables Selected for Capturing Changes](make-changes-to-the-tables-selected-for-capturing-changes.md).</span></span>  
  
 <span data-ttu-id="2fee9-120">**Remover**</span><span class="sxs-lookup"><span data-stu-id="2fee9-120">**Remove**</span></span>  
 <span data-ttu-id="2fee9-121">Selecione uma tabela da lista e clique em **Remover** para remover a tabela da instância CDC.</span><span class="sxs-lookup"><span data-stu-id="2fee9-121">Select a table from the list and click **Remove** to remove the table from the CDC instance.</span></span>  
  
 <span data-ttu-id="2fee9-122">Depois que você [Selecionar tabelas Oracle para capturar alterações](select-oracle-tables-for-capturing-changes.md) e/ou [Fizer alterações nas tabelas selecionadas para capturar alterações](make-changes-to-the-tables-selected-for-capturing-changes.md) usando as caixas de diálogo corretas, clique em **Avançar** para [Gerar e executar scripts de log suplementares](generate-and-run-the-supplemental-logging-script.md).</span><span class="sxs-lookup"><span data-stu-id="2fee9-122">After you [Select Oracle Tables for Capturing Changes](select-oracle-tables-for-capturing-changes.md) and/or [Make Changes to the Tables Selected for Capturing Changes](make-changes-to-the-tables-selected-for-capturing-changes.md) using the correct dialog boxes, click **Next** to [Generate and Run the Supplemental Logging Script](generate-and-run-the-supplemental-logging-script.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fee9-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2fee9-123">See Also</span></span>  
 <span data-ttu-id="2fee9-124">[Como criar a instância de banco de dados de alteração do SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="2fee9-124">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 <span data-ttu-id="2fee9-125">[Editar tabelas](edit-tables.md) </span><span class="sxs-lookup"><span data-stu-id="2fee9-125">[Edit Tables](edit-tables.md) </span></span>  
 <span data-ttu-id="2fee9-126">[Adicionar tabelas a uma instância CDC](add-tables-to-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="2fee9-126">[Add Tables to a CDC Instance](add-tables-to-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="2fee9-127">Editar as propriedades da tabela</span><span class="sxs-lookup"><span data-stu-id="2fee9-127">Edit the Table Properties</span></span>](edit-the-table-properties.md)  
  
  
