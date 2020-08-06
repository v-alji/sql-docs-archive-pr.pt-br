---
title: Como preparar o SQL Server para CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a327fa18-58f4-4e69-bb87-44faf47e20ef
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fbd285faaa55a28ad82beb673fa783570809bd04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678269"
---
# <a name="how-to-prepare-sql-server-for-cdc"></a><span data-ttu-id="1835f-102">Como Preparar o SQL Server para CDC</span><span class="sxs-lookup"><span data-stu-id="1835f-102">How to Prepare SQL Server for CDC</span></span>
  <span data-ttu-id="1835f-103">O serviço Oracle CDC exige que todas as instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino contenham o banco de dados MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="1835f-103">The Oracle CDC service requires all target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances to contain the MSXDBCDC database.</span></span> <span data-ttu-id="1835f-104">Você cria este banco de dados usando a ação Preparar SQL Server no Console de Configuração do Serviço CDC. Esta tarefa é feita uma vez somente para cada instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino.</span><span class="sxs-lookup"><span data-stu-id="1835f-104">You create this database using the Prepare SQL Server action in the CDC Service Configuration Console.This task is done one time only for each target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="1835f-105">Veja a seguir uma descrição sobre como preparar um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para Change Data Capture da Oracle usando o Console de Configuração do Serviço CDC.</span><span class="sxs-lookup"><span data-stu-id="1835f-105">The following describes how to prepare a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database for Oracle Change Data Capture using the CDC Service Configuration Console.</span></span> <span data-ttu-id="1835f-106">Este processo cria o banco de dados MSXDBCDC e define as tabelas necessárias, os procedimentos armazenados e outros artefatos necessários.</span><span class="sxs-lookup"><span data-stu-id="1835f-106">This process creates the MSXDBCDC database and defines the required tables, stored procedures, and other required artifacts.</span></span>  
  
 <span data-ttu-id="1835f-107">A preparação do SQL Server para Oracle CDC é feito pelo Administrador de Serviço Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="1835f-107">Preparing the SQL Server for Oracle CDC is done by the Oracle CDC Service Administrator.</span></span> <span data-ttu-id="1835f-108">Para obter mais informações sobre a função de administrador de serviço CDC, consulte [funções de usuário para o serviço de captura de dados de alterações para Oracle por Attunity](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1835f-108">For more information about the CDC Service Administrator role, see [User Roles for Change Data Capture Service for Oracle by Attunity](user-roles.md).</span></span>  
  
### <a name="to-enable-sql-server-for-cdc"></a><span data-ttu-id="1835f-109">Para habilitar o SQL Server para CDC</span><span class="sxs-lookup"><span data-stu-id="1835f-109">To enable SQL Server for CDC</span></span>  
  
1.  <span data-ttu-id="1835f-110">No menu **Iniciar** , selecione **Configuração do Serviço CDC para Oracle**.</span><span class="sxs-lookup"><span data-stu-id="1835f-110">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="1835f-111">No painel esquerdo, selecione **Serviços Locais CDC** no painel **Ações** e clique em **Preparar SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="1835f-111">From the left pane, select **Local CDC Services** then from the **Actions** pane, click **Prepare SQL Server**.</span></span>  
  
     <span data-ttu-id="1835f-112">Você também pode clicar com o botão direito do mouse em **Local CDC Services (Serviços Locais de CDC)** e selecionar **Prepare SQL Server (Preparar SQL Server)** .</span><span class="sxs-lookup"><span data-stu-id="1835f-112">You can also right-click **Local CDC Services** and select **Prepare SQL Server**.</span></span>  
  
3.  <span data-ttu-id="1835f-113">Insira as informações necessárias na caixa de diálogo Preparando a Instância SQL Server para Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="1835f-113">Enter the required information in the Preparing SQL Server Instance for Oracle CDC dialog box.</span></span> <span data-ttu-id="1835f-114">Para obter informações sobre como inserir as informações necessárias nessa caixa de diálogo, consulte [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="1835f-114">For information on how to enter the required information into this dialog box, see [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span></span>  
  
     <span data-ttu-id="1835f-115">Para Preparar a instância do SQL Server para Oracle CDC, o logon deve ter permissão de gravação no banco de dados MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="1835f-115">To Prepare the SQL Server instance for Oracle CDC, the login must have write permission to the MSXDBCDC database.</span></span> <span data-ttu-id="1835f-116">Insira as credenciais para um logon que tem permissão de gravação no banco de dados MSXDBCDC, como um membro da função `sysasmin` .</span><span class="sxs-lookup"><span data-stu-id="1835f-116">Enter the credentials for a login that has write permission to the MSXDBCDC database, such as a member of the `sysasmin` role.</span></span>  
  
 <span data-ttu-id="1835f-117">**Observação**: clique em **Exibir Script** para exibir uma versão somente leitura do script de instalação.</span><span class="sxs-lookup"><span data-stu-id="1835f-117">**Note**: You can click **View Script** to view a read-only version of the setup script.</span></span> <span data-ttu-id="1835f-118">Um administrador do sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode copiar este script no Console de Gerenciamento do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para editá-lo e executá-lo, se for necessário.</span><span class="sxs-lookup"><span data-stu-id="1835f-118">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator can copy this script into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Console to edit and execute it, if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1835f-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1835f-119">See Also</span></span>  
 [<span data-ttu-id="1835f-120">Preparar o SQL Server para CDC</span><span class="sxs-lookup"><span data-stu-id="1835f-120">Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
