---
title: Alterar a disponibilidade de um operador | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- canceling operators
- reactivating operators
- removing operators
- deleting operators
- available operators [SQL Server]
- dropping operators
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
- disabling operators
- operators (users) [Database Engine], changing availability with Management Studio
ms.assetid: 10d58b92-b67b-47e2-af9c-9f9fd6968bba
author: stevestein
ms.author: sstein
ms.openlocfilehash: fb369ea6a2d1edf1ed8f4377b627fb1ba7339a03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583335"
---
# <a name="change-an-operator39s-availability"></a><span data-ttu-id="79081-102">Alterar a disponibilidade de um operador</span><span class="sxs-lookup"><span data-stu-id="79081-102">Change an Operator&#39;s Availability</span></span>
  <span data-ttu-id="79081-103">Este tópico descreve como alterar a agenda de um operador para receber notificações de alerta no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79081-103">This topic describes how to change an operator's schedule for receiving alert notifications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="79081-104">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="79081-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="79081-105">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="79081-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="79081-106">Segurança</span><span class="sxs-lookup"><span data-stu-id="79081-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="79081-107">**Para alterar a disponibilidade de um operador usando:**</span><span class="sxs-lookup"><span data-stu-id="79081-107">**To change an operator's availability, using:**</span></span>  
  
     [<span data-ttu-id="79081-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="79081-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="79081-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="79081-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="79081-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="79081-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="79081-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="79081-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="79081-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="79081-112">Permissions</span></span>  
 <span data-ttu-id="79081-113">Somente membros da função de servidor fixa **sysadmin** podem editar operadores.</span><span class="sxs-lookup"><span data-stu-id="79081-113">Only members of the **sysadmin** fixed server role can edit operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="79081-114">Usando o SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="79081-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-an-operators-availability"></a><span data-ttu-id="79081-115">Para alterar a disponibilidade de um operador</span><span class="sxs-lookup"><span data-stu-id="79081-115">To change an operator's availability</span></span>  
  
1.  <span data-ttu-id="79081-116">No **Pesquisador de Objetos**, clique no sinal de adição para expandir o servidor que contém o operador que você deseja habilitar ou desabilitar.</span><span class="sxs-lookup"><span data-stu-id="79081-116">In **Object Explorer**, click the plus sign to expand server that contains the operator that you want to enable or disable.</span></span>  
  
2.  <span data-ttu-id="79081-117">Clique no sinal de adição para expandir o **SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="79081-117">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="79081-118">Clique no sinal de adição para expandir a pasta **Operadores** .</span><span class="sxs-lookup"><span data-stu-id="79081-118">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="79081-119">Clique com o botão direito do mouse no operador que deseja habilitar ou desabilitar e selecione **Propriedades**e clique na guia **Geral** .</span><span class="sxs-lookup"><span data-stu-id="79081-119">Right-click the operator that you want to enable or disable and select **Properties**, then click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="79081-120">Na caixa de diálogo**Propriedades** do _operator_name_, marque ou desmarque a caixa de seleção **habilitado** .</span><span class="sxs-lookup"><span data-stu-id="79081-120">In the _operator_name_**Properties** dialog box, select or clear the **Enabled** check box.</span></span>  
  
6.  <span data-ttu-id="79081-121">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="79081-121">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="79081-122">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="79081-122">Using Transact-SQL</span></span>  
  
#### <a name="to-change-an-operators-availability"></a><span data-ttu-id="79081-123">Para alterar a disponibilidade de um operador</span><span class="sxs-lookup"><span data-stu-id="79081-123">To change an operator's availability</span></span>  
  
1.  <span data-ttu-id="79081-124">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79081-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="79081-125">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="79081-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="79081-126">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="79081-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- disables the 'Fran??ois Ajenstat' operator  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_operator   
        @name = N'Fran??ois Ajenstat',  
        @enabled = 0;  
    GO  
    ```  
  
 <span data-ttu-id="79081-127">Para obter mais informações, consulte [sp_update_operator &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="79081-127">For more information, see [sp_update_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span></span>  
  
  
