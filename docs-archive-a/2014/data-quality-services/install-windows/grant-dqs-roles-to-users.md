---
title: Conceder funções DQS a usuários | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: afb445b5-bdbe-4bfe-844f-344766cdc2b2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 62ff5eb03fa46279ee1b8a1329c58bd69361ef82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683684"
---
# <a name="grant-dqs-roles-to-users"></a><span data-ttu-id="dd66f-102">Conceder funções DQS a usuários</span><span class="sxs-lookup"><span data-stu-id="dd66f-102">Grant DQS Roles to Users</span></span>
  <span data-ttu-id="dd66f-103">Este tópico descreve como criar logons do SQL Server com base em uma entidade do Windows e conceder as funções de [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] no banco de dados DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="dd66f-103">This topic describes how to create SQL logins based on a Windows principal, and grant [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) roles on the DQS_MAIN database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dd66f-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="dd66f-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="dd66f-105">Você precisa ter concluído a instalação do [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] executando o arquivo DQSInstaller.exe.</span><span class="sxs-lookup"><span data-stu-id="dd66f-105">You must have completed the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="dd66f-106">Para obter mais informações, consulte [Executar o DQSInstaller.exe para concluir a instalação do Data Quality Server](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="dd66f-106">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
-   <span data-ttu-id="dd66f-107">Sua conta de usuário do Windows deve ser membro da função de servidor fixa apropriada (como securityadmin, serveradmin ou sysadmin) para criar um logon do SQL login e conceder a ele as funções de DQS.</span><span class="sxs-lookup"><span data-stu-id="dd66f-107">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) to create SQL login, and grant them DQS roles.</span></span>  
  
### <a name="to-create-sql-login-and-grant-dqs-roles"></a><span data-ttu-id="dd66f-108">Para criar logon de SQL e conceder funções de DQS</span><span class="sxs-lookup"><span data-stu-id="dd66f-108">To create SQL login and grant DQS roles</span></span>  
  
1.  <span data-ttu-id="dd66f-109">Inicie o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd66f-109">Start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="dd66f-110">Em [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda sua instância do SQL Server e expanda **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="dd66f-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand your SQL Server instance, and then expand **Security**.</span></span>  
  
3.  <span data-ttu-id="dd66f-111">Clique com o botão direito do mouse na pasta **Segurança** , aponte para **Novo**e clique em **Logon**.</span><span class="sxs-lookup"><span data-stu-id="dd66f-111">Right-click the **Security** folder, point to **New**, and then click **Login**.</span></span>  
  
4.  <span data-ttu-id="dd66f-112">Na caixa de diálogo **logon – novo** , especifique o nome de um usuário do Windows na caixa **nome de logon** , especifique o tipo de autenticação como autenticação do **Windows**e clique em **Pesquisar** para validar o usuário.</span><span class="sxs-lookup"><span data-stu-id="dd66f-112">In the **Login - New** dialog box, specify the name of a Windows user in the **Login name** box, specify the type of authentication as **Windows authentication**, and click **Search** to validate the user.</span></span>  
  
5.  <span data-ttu-id="dd66f-113">Depois que o usuário for validado, clique na página **Mapeamento de Usuário** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="dd66f-113">After the user is validated, click the **User Mapping** page in the left pane.</span></span>  
  
6.  <span data-ttu-id="dd66f-114">No painel direito, marque a caixa de seleção sob a coluna **Mapa** do banco de dados **DQS_MAIN** e marque a caixa de seleção **dqs_administrator**, **dqs_kb_editor**ou **dqs_kb_operator** no painel **Associação à função de banco de dados para: DQS_MAIN** , dependendo do nível de acesso necessário ao usuário.</span><span class="sxs-lookup"><span data-stu-id="dd66f-114">In the right pane, select the check box under the **Map** column for the **DQS_MAIN** database, and then select the **dqs_administrator**, **dqs_kb_editor**, or **dqs_kb_operator** check box in the **Database role membership for: DQS_MAIN** pane, depending on the access level needed for the user.</span></span> <span data-ttu-id="dd66f-115">Para obter mais informações sobre as três funções DQS, consulte [Segurança DQS](../dqs-security.md).</span><span class="sxs-lookup"><span data-stu-id="dd66f-115">For information about the three DQS roles, see [DQS Security](../dqs-security.md).</span></span>  
  
7.  <span data-ttu-id="dd66f-116">Na caixa de diálogo **Logon – Novo**, clique em **OK** para aplicar as alterações.</span><span class="sxs-lookup"><span data-stu-id="dd66f-116">In the **Login - New** dialog box, click **OK** to apply the changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dd66f-117">Se você conceder a função **dqs_administrator** a um usuário, aplique as alterações e verifique novamente as permissões de usuário; as outras duas caixas de seleção de funções DQS (**dq_kb_editor** e **dqs_kb_operator**) também serão marcadas.</span><span class="sxs-lookup"><span data-stu-id="dd66f-117">If you grant the **dqs_administrator** role to a user, apply the changes, and then recheck the user permissions, the other two DQS roles check boxes (**dq_kb_editor** and **dqs_kb_operator**) are also selected.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="dd66f-118">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="dd66f-118">Next Steps</span></span>  
 <span data-ttu-id="dd66f-119">Tente fazer logon no [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] usando a conta de usuário do Windows para a qual você acabou de criar o logon SQL e à qual concedeu uma função DQS.</span><span class="sxs-lookup"><span data-stu-id="dd66f-119">Try logging on to [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] by using the Windows user account for which you just created a SQL login, and granted a DQS role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd66f-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dd66f-120">See Also</span></span>  
 <span data-ttu-id="dd66f-121">[Instalar o Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="dd66f-121">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="dd66f-122">Criar um logon</span><span class="sxs-lookup"><span data-stu-id="dd66f-122">Create a Login</span></span>](../../relational-databases/security/authentication-access/create-a-login.md)  
  
  
