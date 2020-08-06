---
title: Editar Tabelas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- tabProps
ms.assetid: fed8fada-2abc-45e2-8228-0656f9c599cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8e8058a0c3e8b81814283f055e4c4ac2b08dd2fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569591"
---
# <a name="edit-tables"></a><span data-ttu-id="e408f-102">Editar tabelas</span><span class="sxs-lookup"><span data-stu-id="e408f-102">Edit Tables</span></span>
  <span data-ttu-id="e408f-103">Use a guia **Tables** para fazer alterações às tabelas e colunas selecionadas do banco de dados de origem Oracle.</span><span class="sxs-lookup"><span data-stu-id="e408f-103">Use the **Tables** tab to make changes to the tables and columns that you selected from the Oracle source database.</span></span> <span data-ttu-id="e408f-104">Esta guia tem os seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="e408f-104">This tab has the following elements:</span></span>  
  
 <span data-ttu-id="e408f-105">**Lista Tabela**</span><span class="sxs-lookup"><span data-stu-id="e408f-105">**Table list**</span></span>  
 <span data-ttu-id="e408f-106">A lista de tabelas tem três colunas:</span><span class="sxs-lookup"><span data-stu-id="e408f-106">The table list has three columns:</span></span>  
  
-   <span data-ttu-id="e408f-107">**Nome da tabela Oracle**: o nome da tabela, incluindo esquema de tabela.</span><span class="sxs-lookup"><span data-stu-id="e408f-107">**Oracle Table Name**: The name of the table, including the table schema.</span></span>  
  
-   <span data-ttu-id="e408f-108">**Instância de Captura**: é o nome da instância de captura usada para nomear objetos do Change Data Capture específicos.</span><span class="sxs-lookup"><span data-stu-id="e408f-108">**Capture Instance**: The name of the capture instance used to name instance-specific change data capture objects.</span></span> <span data-ttu-id="e408f-109">A instância de captura não pode ser NULL.</span><span class="sxs-lookup"><span data-stu-id="e408f-109">The capture instance cannot be NULL.</span></span> <span data-ttu-id="e408f-110">Se não for especificado, o nome será derivado do nome do esquema de origem mais o nome da tabela de origem, no formato `<schema-name>_<table-name>.` . O nome da instância de captura não pode exceder a 100 caracteres e deve ser exclusivo dentro do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e408f-110">If not specified, the name is derived from the source schema name plus the source table name in the format `<schema-name>_<table-name>.` The capture instance name cannot exceed 100 characters and must be unique within the database.</span></span> <span data-ttu-id="e408f-111">Você pode clicar em qualquer célula nesta coluna para editar manualmente **capture_instance**.</span><span class="sxs-lookup"><span data-stu-id="e408f-111">You can click in any cell in this column to manually edit the **capture_instance**.</span></span>  
  
-   <span data-ttu-id="e408f-112">**Security Role**: o nome da função de banco de dados usada para obter acesso aos dados de alteração.</span><span class="sxs-lookup"><span data-stu-id="e408f-112">**Security Role**: The name of the database role used to gain access to change data.</span></span> <span data-ttu-id="e408f-113">Você pode clicar em qualquer célula nesta coluna para editar manualmente **security_role**.</span><span class="sxs-lookup"><span data-stu-id="e408f-113">You can click in any cell in this column to manually edit the **security_role**.</span></span>  
  
 <span data-ttu-id="e408f-114">**Adicionar tabelas**</span><span class="sxs-lookup"><span data-stu-id="e408f-114">**Add Tables**</span></span>  
 <span data-ttu-id="e408f-115">Clique em **Adicionar Tabelas** para abrir a caixa de diálogo Seleção de Tabela em que você pode [Adicionar tabelas a uma instância CDC](add-tables-to-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="e408f-115">Click **Add Tables** to open the Table Selection dialog box where you can [Add Tables to a CDC Instance](add-tables-to-a-cdc-instance.md).</span></span> <span data-ttu-id="e408f-116">Da primeira vez nesta sessão que você acessa o banco de dados Oracle, é preciso [Connect to Oracle](connect-to-oracle.md).</span><span class="sxs-lookup"><span data-stu-id="e408f-116">The first time this session that you access the Oracle database, you must [Connect to Oracle](connect-to-oracle.md).</span></span>  
  
 <span data-ttu-id="e408f-117">**Editar**</span><span class="sxs-lookup"><span data-stu-id="e408f-117">**Edit**</span></span>  
 <span data-ttu-id="e408f-118">Selecione uma tabela da lista e selecione **Editar** para abrir a caixa de diálogo **Propriedades** para a tabela em que você pode [Editar as propriedades da tabela](edit-the-table-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e408f-118">Select a table from the list and select **Edit** to open the **Properties** dialog box for that table where you can [Edit the Table Properties](edit-the-table-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e408f-119">Você não pode editar o mapeamento de tipo para tabelas que já tenham tabelas de espelho.</span><span class="sxs-lookup"><span data-stu-id="e408f-119">You cannot edit type mapping for tables that already have mirror tables.</span></span> <span data-ttu-id="e408f-120">Você só pode fazer isto para novas tabelas.</span><span class="sxs-lookup"><span data-stu-id="e408f-120">You can do this for new tables only.</span></span>  
  
 <span data-ttu-id="e408f-121">**Remover**</span><span class="sxs-lookup"><span data-stu-id="e408f-121">**Remove**</span></span>  
 <span data-ttu-id="e408f-122">Selecione uma tabela da lista e clique em **Remover** para remover a tabela da instância CDC.</span><span class="sxs-lookup"><span data-stu-id="e408f-122">Select a table from the list and click **Remove** to remove the table from the CDC instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e408f-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e408f-123">See Also</span></span>  
 <span data-ttu-id="e408f-124">[Como editar as propriedades de instância CDC](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="e408f-124">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="e408f-125">Selecionar tabelas e colunas Oracle</span><span class="sxs-lookup"><span data-stu-id="e408f-125">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
