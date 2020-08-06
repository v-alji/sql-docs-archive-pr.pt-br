---
title: Acessar dados para as operações do DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 88dfb9ea-6321-4eaf-b9e4-45d36ef048f6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 515b087a8d16e44314d1a21d3dfbd6f13c767f5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681216"
---
# <a name="access-data-for-the-dqs-operations"></a><span data-ttu-id="854ce-102">Acessar dados para as operações do DQS</span><span class="sxs-lookup"><span data-stu-id="854ce-102">Access Data for the DQS Operations</span></span>
  <span data-ttu-id="854ce-103">Para usar seus dados de origem para operações do [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) e exportar seus dados processados, você pode adotar um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="854ce-103">To use your source data for [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) operations, and export your processed data, you can do either of the following:</span></span>  
  
-   <span data-ttu-id="854ce-104">Copiar seus dados de origem em uma tabela/exibição no banco de dados DQS_STAGING_DATA e, depois, usá-los em operações do DQS.</span><span class="sxs-lookup"><span data-stu-id="854ce-104">Copy your source data to a table/view in the DQS_STAGING_DATA database, and then use it for DQS operations.</span></span> <span data-ttu-id="854ce-105">Você também pode exportar os dados processados para uma nova tabela no banco de dados DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="854ce-105">You can also export the processed data to a new table in the DQS_STAGING_DATA database.</span></span> <span data-ttu-id="854ce-106">Para isso, sua conta de usuário do Windows deve ter acesso de leitura/gravação ao banco de dados DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="854ce-106">To do so, your Windows user account must be granted read/write access to the DQS_STAGING_DATA database.</span></span>  
  
-   <span data-ttu-id="854ce-107">Use seu próprio banco de dados como os dados de origem em operações do DQS e destino para exportar os dados processados.</span><span class="sxs-lookup"><span data-stu-id="854ce-107">Use your own database as the source data for the DQS operations, and destination for exporting the processed data.</span></span> <span data-ttu-id="854ce-108">Para fazer isso, verifique se o banco de dados está na mesma instância do SQL Server que os bancos de dados do Data Quality Server.</span><span class="sxs-lookup"><span data-stu-id="854ce-108">To do so, ensure that your database is in the same SQL Server instance as the Data Quality Server databases.</span></span> <span data-ttu-id="854ce-109">Caso contrário, o banco de dados não estará disponível no cliente Data Quality para operações do DQS.</span><span class="sxs-lookup"><span data-stu-id="854ce-109">Otherwise, the database will not be available in the Data Quality Client for DQS operations.</span></span> <span data-ttu-id="854ce-110">Além disso, sua conta de usuário do Windows deve ter acesso ao banco de dados DQS_STAGING_DATA para exportar os resultados compatíveis porque eles são exportados em duas fases: primeiro, os resultados compatíveis são exportados para as tabelas temporárias no banco de dados DQS_STAGING_DATA e, em seguida, são movidos para a tabela no banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="854ce-110">Also, your Windows user account must be granted access on the DQS_STAGING_DATA database for exporting the matching results because matching results are exported in two phases: first, the matching results are exported to the temporary tables in the DQS_STAGING_DATA database, and then moved to the table in your destination database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="854ce-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="854ce-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="854ce-112">Você precisa ter concluído a instalação do [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] executando o arquivo DQSInstaller.exe.</span><span class="sxs-lookup"><span data-stu-id="854ce-112">You must have completed the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="854ce-113">Para obter mais informações, consulte [Executar o DQSInstaller.exe para concluir a instalação do Data Quality Server](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="854ce-113">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
-   <span data-ttu-id="854ce-114">Sua conta de usuário do Windows deve ser um membro da função de servidor fixa apropriada (como securityadmin, serveradmin ou sysadmin) na instância do mecanismo de banco de dados para conceder/modificar o acesso ao logon do SQL em bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="854ce-114">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) in the database engine instance to grant/modify access to SQL login on databases.</span></span>  
  
### <a name="to-grant-readwrite-access-to-a-user-on-the-dqs_staging_data-database"></a><span data-ttu-id="854ce-115">Para conceder acesso de leitura/gravação a um Usuário no banco de dados DQS_STAGING_DATA</span><span class="sxs-lookup"><span data-stu-id="854ce-115">To grant read/write access to a User on the DQS_STAGING_DATA Database</span></span>  
  
1.  <span data-ttu-id="854ce-116">Inicie o Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="854ce-116">Start Microsoft SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="854ce-117">No Microsoft SQL Server Management Studio, expanda sua instância do SQL Server, expanda **Segurança**e, depois, expanda **Logons**.</span><span class="sxs-lookup"><span data-stu-id="854ce-117">In Microsoft SQL Server Management Studio, expand your SQL Server instance, and expand **Security**, and then expand **Logins**.</span></span>  
  
3.  <span data-ttu-id="854ce-118">Clique com o botão direito do mouse em um logon do SQL e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="854ce-118">Right-click a SQL login, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="854ce-119">Na caixa de diálogo **Propriedades de Logon** , clique na página **Mapeamento de Usuário** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="854ce-119">In the **Login Properties** dialog box, click the **User Mapping** page in the left pane.</span></span>  
  
5.  <span data-ttu-id="854ce-120">No painel direito, marque a caixa de seleção na coluna **Mapa** do banco de dados **DQS_STAGING_DATA** e selecione as seguintes funções no painel **Associação à função de banco de dados para: DQS_STAGING_DATA** :</span><span class="sxs-lookup"><span data-stu-id="854ce-120">In the right pane, select the check box under the **Map** column for the **DQS_STAGING_DATA** database, and then select the following roles in the **Database role membership for: DQS_STAGING_DATA** pane:</span></span>  
  
    -   <span data-ttu-id="854ce-121">**db_datareader**: ler dados de tabelas/exibições.</span><span class="sxs-lookup"><span data-stu-id="854ce-121">**db_datareader**: Read data from tables/views.</span></span>  
  
    -   <span data-ttu-id="854ce-122">**db_datawriter**: adicionar, excluir ou alterar dados em tabelas.</span><span class="sxs-lookup"><span data-stu-id="854ce-122">**db_datawriter**: Add, delete, or change data in tables.</span></span>  
  
    -   <span data-ttu-id="854ce-123">**db_ddladmin**: criar, modificar ou excluir tabelas/exibições.</span><span class="sxs-lookup"><span data-stu-id="854ce-123">**db_ddladmin**: Create, modify, or delete tables/views.</span></span>  
  
6.  <span data-ttu-id="854ce-124">Na caixa de diálogo **Propriedades** , clique em **OK** para aplicar as alterações.</span><span class="sxs-lookup"><span data-stu-id="854ce-124">In the **Login Properties** dialog box, click **OK** to apply the changes.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="854ce-125">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="854ce-125">Next Steps</span></span>  
 <span data-ttu-id="854ce-126">Tente realizar operações do DQS que acessam o banco de dados como fonte de dados para a operação DQS e, em seguida, exportam os dados processados para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="854ce-126">Try performing DQS operations that accesses the database as data source for DQS operation, and then exports the processed data to the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="854ce-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="854ce-127">See Also</span></span>  
 [<span data-ttu-id="854ce-128">Instalar o Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="854ce-128">Install Data Quality Services</span></span>](install-data-quality-services.md)  
  
  
