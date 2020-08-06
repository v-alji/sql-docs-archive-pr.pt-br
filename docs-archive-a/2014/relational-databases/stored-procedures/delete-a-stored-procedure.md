---
title: Excluir um procedimento armazenado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- removing stored procedures
- stored procedures [SQL Server], deleting
- deleting stored procedures
ms.assetid: 232dbf4d-392a-406f-af3a-579518cd8e46
author: stevestein
ms.author: sstein
ms.openlocfilehash: 418e68d4bb7c6ba6632767a554aea72e85726840
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582345"
---
# <a name="delete-a-stored-procedure"></a><span data-ttu-id="d6d05-102">Excluir um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="d6d05-102">Delete a Stored Procedure</span></span>
    
##  <a name="this-topic-describes-how-to-delete-a-stored-procedure-in-sscurrent-by-using-ssmanstudiofull-or-tsql"></a><a name="Top"></a> <span data-ttu-id="d6d05-103">Este tópico descreve como excluir um procedimento armazenado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6d05-103">This topic describes how to delete a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="d6d05-104">**Antes de começar:**  [Limitações e Restrições](#Restrictions), [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="d6d05-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="d6d05-105">**Para excluir um procedimento usando:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="d6d05-105">**To delete a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d6d05-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="d6d05-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d6d05-107">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="d6d05-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="d6d05-108">Excluir um procedimento pode causar a falha em objetos e scripts dependentes quando os objetos e scripts não são atualizados para refletir a remoção do procedimento.</span><span class="sxs-lookup"><span data-stu-id="d6d05-108">Deleting a procedure can cause dependent objects and scripts to fail when the objects and scripts are not updated to reflect the removal of the procedure.</span></span> <span data-ttu-id="d6d05-109">Entretanto, se um novo procedimento com o mesmo nome e o mesmo parâmetro for criado para substituir aquele que foi excluído, os outros objetos que o referenciam ainda serão processados com êxito.</span><span class="sxs-lookup"><span data-stu-id="d6d05-109">However, if a new procedure of the same name and the same parameters is created to replace the one that was deleted, other objects that reference it will still process successfully.</span></span> <span data-ttu-id="d6d05-110">Para obter mais informações, veja [Exibir as dependências de um procedimento armazenado](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="d6d05-110">For more information, see [View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d6d05-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="d6d05-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d6d05-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="d6d05-112">Permissions</span></span>  
 <span data-ttu-id="d6d05-113">Requer permissão ALTER no esquema ao qual o procedimento pertence ou permissão CONTROL no procedimento.</span><span class="sxs-lookup"><span data-stu-id="d6d05-113">Requires ALTER permission on the schema to which the procedure belongs, or CONTROL permission on the procedure.</span></span>  
  
##  <a name="how-to-delete-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="d6d05-114">Como excluir um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="d6d05-114">How to Delete a Stored Procedure</span></span>  
 <span data-ttu-id="d6d05-115">Você pode usar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="d6d05-115">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="d6d05-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d6d05-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="d6d05-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d6d05-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d6d05-118">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d6d05-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="d6d05-119">**Para excluir um procedimento no Pesquisador de Objetos**</span><span class="sxs-lookup"><span data-stu-id="d6d05-119">**To delete a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="d6d05-120">No Pesquisador de Objetos, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="d6d05-120">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d6d05-121">Expanda **Bancos de Dados**, expanda o banco de dados ao qual pertence o procedimento e expanda **Programação**.</span><span class="sxs-lookup"><span data-stu-id="d6d05-121">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="d6d05-122">Expanda **Procedimentos Armazenados**, clique com o botão direito do mouse no procedimento a excluir e, depois, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="d6d05-122">Expand **Stored Procedures**, right-click the procedure to remove, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="d6d05-123">Para exibir objetos que dependem do procedimento, clique em **Mostrar Dependências**.</span><span class="sxs-lookup"><span data-stu-id="d6d05-123">To view objects that depend on the procedure, click **Show Dependencies**.</span></span>  
  
5.  <span data-ttu-id="d6d05-124">Confirme se o procedimento correto está selecionado e, depois, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d6d05-124">Confirm the correct procedure is selected, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="d6d05-125">Remova as referências ao procedimento de quaisquer objetos e scripts dependentes.</span><span class="sxs-lookup"><span data-stu-id="d6d05-125">Remove references to the procedure from any dependent objects and scripts.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d6d05-126">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d6d05-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="d6d05-127">**Para excluir um procedimento no Editor de Consultas**</span><span class="sxs-lookup"><span data-stu-id="d6d05-127">**To delete a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="d6d05-128">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e expanda-a.</span><span class="sxs-lookup"><span data-stu-id="d6d05-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d6d05-129">Expanda **Bancos de dados**, expanda o banco de dados ao qual o procedimento pertence, ou, da barra de ferramentas, selecione o banco de dados da lista de bancos de dados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d6d05-129">Expand **Databases**, expand the database in which the procedure belongs, or, from the tool bar, select the database from the list of available databases.</span></span>  
  
3.  <span data-ttu-id="d6d05-130">No menu Arquivo, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="d6d05-130">On the File menu, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="d6d05-131">Obtenha o nome do procedimento armazenado a ser removido no banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="d6d05-131">Obtain the name of stored procedure to remove in the current database.</span></span> <span data-ttu-id="d6d05-132">No Pesquisador de Objetos, expanda **Programação** e, depois, expanda **Procedimentos Armazenados**.</span><span class="sxs-lookup"><span data-stu-id="d6d05-132">From Object Explorer, expand **Programmability** and then expand **Stored Procedures**.</span></span> <span data-ttu-id="d6d05-133">Outra alternativa é executar a instrução a seguir no editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="d6d05-133">Alternatively, in the query editor, run the following statement.</span></span>  
  
    ```sql  
    SELECT name AS procedure_name   
        ,SCHEMA_NAME(schema_id) AS schema_name  
        ,type_desc  
        ,create_date  
        ,modify_date  
    FROM sys.procedures;  
    ```  
  
5.  <span data-ttu-id="d6d05-134">Copie e cole o exemplo a seguir no editor de consultas e insira um nome de procedimento armazenado a ser excluído do banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="d6d05-134">Copy and paste the following example into the query editor and insert a stored procedure name to delete from the current database.</span></span>  
  
    ```sql  
    DROP PROCEDURE <stored procedure name>;  
    GO  
    ```  
  
6.  <span data-ttu-id="d6d05-135">Remova as referências ao procedimento de quaisquer objetos e scripts dependentes.</span><span class="sxs-lookup"><span data-stu-id="d6d05-135">Remove references to the procedure from any dependent objects and scripts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6d05-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d6d05-136">See Also</span></span>  
 <span data-ttu-id="d6d05-137">[Criar um procedimento armazenado](create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="d6d05-137">[Create a Stored Procedure](create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="d6d05-138">[Modificar um procedimento armazenado](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="d6d05-138">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="d6d05-139">[Renomear um procedimento armazenado](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="d6d05-139">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="d6d05-140">[Exibir a definição de um procedimento armazenado](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="d6d05-140">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="d6d05-141">[Exibir as dependências de um procedimento armazenado](view-the-dependencies-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="d6d05-141">[View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="d6d05-142">DROP PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d6d05-142">DROP PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-procedure-transact-sql)  
  
  
