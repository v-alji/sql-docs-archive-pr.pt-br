---
title: Gerenciar usuários do DQS no SSMS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 955af01d-00da-4c51-9311-f3848749df54
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bf8789abb59d168f39562f6486bb5c54bfc0fc50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582621"
---
# <a name="manage-dqs-users-in-ssms"></a><span data-ttu-id="62553-102">Gerenciar usuários de DQS em SSMS</span><span class="sxs-lookup"><span data-stu-id="62553-102">Manage DQS Users in SSMS</span></span>
  <span data-ttu-id="62553-103">Este tópico descreve como criar usuários adicionais na instância do SQL Server usando o SQL Server Management Studio e como concedê-los funções DQS apropriadas do [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] no banco de dados DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="62553-103">This topic describes how to create additional users in the SQL Server instance using SQL Server Management Studio, and grant them appropriate [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) roles on the DQS_MAIN database.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="62553-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="62553-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="62553-105">Segurança</span><span class="sxs-lookup"><span data-stu-id="62553-105">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="62553-106">Permissões</span><span class="sxs-lookup"><span data-stu-id="62553-106">Permissions</span></span>  
 <span data-ttu-id="62553-107">Sua conta de usuário do Windows deve ser membro da função de servidor fixa apropriada (como securityadmin, serveradmin ou sysadmin) para criar um logon do SQL e conceder funções DQS adequadas.</span><span class="sxs-lookup"><span data-stu-id="62553-107">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) to create SQL login, and grant appropriate DQS roles.</span></span>  
  
##  <a name="create-a-sql-login-and-grant-dqs-role"></a><a name="GrantRoles"></a><span data-ttu-id="62553-108">Criar um logon do SQL e conceder a função DQS</span><span class="sxs-lookup"><span data-stu-id="62553-108">Create a SQL Login and Grant DQS Role</span></span>  
  
1.  <span data-ttu-id="62553-109">Inicie o Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="62553-109">Start Microsoft SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="62553-110">Em Microsoft SQL Server Management Studio, expanda sua instância do SQL Server e expanda **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="62553-110">In Microsoft SQL Server Management Studio, expand your SQL Server instance, and then expand **Security**.</span></span>  
  
3.  <span data-ttu-id="62553-111">Clique com o botão direito do mouse na pasta **Segurança** , aponte para **Novo**e clique em **Logon**.</span><span class="sxs-lookup"><span data-stu-id="62553-111">Right-click the **Security** folder, point to **New**, and then click **Login**.</span></span>  
  
4.  <span data-ttu-id="62553-112">Na caixa de diálogo **logon – novo** , especifique o nome de um usuário do Windows na caixa **nome de logon** , especifique o tipo de autenticação como autenticação do **Windows**e clique em **Pesquisar** para validar o usuário.</span><span class="sxs-lookup"><span data-stu-id="62553-112">In the **Login - New** dialog box, specify the name of a Windows user in the **Login name** box, specify the type of authentication as **Windows authentication**, and click **Search** to validate the user.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="62553-113">O DQS dá suporte somente à autenticação do Windows; a autenticação do SQL Server não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="62553-113">DQS only supports Windows authentication; SQL Server authentication is not supported.</span></span>  
  
5.  <span data-ttu-id="62553-114">Depois que o usuário for validado, clique na página **Mapeamento de Usuário** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="62553-114">After the user is validated, click the **User Mapping** page in the left pane.</span></span>  
  
6.  <span data-ttu-id="62553-115">No painel direito, marque a caixa de seleção sob a coluna **Mapa** do banco de dados **DQS_MAIN** e marque a caixa de seleção **dqs_administrator**, **dqs_kb_editor**ou **dqs_kb_operator** no painel **Associação à função de banco de dados para: DQS_MAIN** , dependendo do nível de acesso necessário ao usuário.</span><span class="sxs-lookup"><span data-stu-id="62553-115">In the right pane, select the check box under the **Map** column for the **DQS_MAIN** database, and then select the **dqs_administrator**, **dqs_kb_editor**, or **dqs_kb_operator** check box in the **Database role membership for: DQS_MAIN** pane, depending on the access level needed for the user.</span></span>  
  
7.  <span data-ttu-id="62553-116">Na caixa de diálogo **Logon – Novo**, clique em **OK** para aplicar as alterações.</span><span class="sxs-lookup"><span data-stu-id="62553-116">In the **Login - New** dialog box, click **OK** to apply the changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="62553-117">Se você conceder a função **dqs_administrator** a um usuário, aplique as alterações e verifique novamente as permissões de usuário; as outras duas caixas de seleção de funções DQS (**dq_kb_editor** e **dqs_kb_operator**) também serão marcadas.</span><span class="sxs-lookup"><span data-stu-id="62553-117">If you grant the **dqs_administrator** role to a user, apply the changes, and then recheck the user permissions, the other two DQS roles check boxes (**dq_kb_editor** and **dqs_kb_operator**) are also selected.</span></span>  
  
  
