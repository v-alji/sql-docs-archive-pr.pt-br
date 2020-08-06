---
title: Conectar a um banco de dados de origem Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraDb
ms.assetid: 220cf555-0db2-443c-8f87-8e413f3ca731
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fccba3d11adc67b3f5ef4f8648ec5d0de07a5648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683142"
---
# <a name="connect-to-an-oracle-source-database"></a><span data-ttu-id="9a9a5-102">Conectar a um banco de dados de origem Oracle</span><span class="sxs-lookup"><span data-stu-id="9a9a5-102">Connect to an Oracle Source Database</span></span>
  <span data-ttu-id="9a9a5-103">Use a página do Oracle de origem para fornecer as informações necessárias para conectar-se ao banco de dados de origem Oracle.</span><span class="sxs-lookup"><span data-stu-id="9a9a5-103">Use the Oracle Source page to provide the information necessary to connect to the Oracle source database.</span></span> <span data-ttu-id="9a9a5-104">A instância CDC lerá os logs de refazer do banco de dados Oracle aos quais você está conectado.</span><span class="sxs-lookup"><span data-stu-id="9a9a5-104">The CDC instance will read the redo logs of the Oracle database you are connected to.</span></span>  
  
 <span data-ttu-id="9a9a5-105">**Cadeia de conexão do Oracle**</span><span class="sxs-lookup"><span data-stu-id="9a9a5-105">**Oracle Connect String**</span></span>  
 <span data-ttu-id="9a9a5-106">Insira a cadeia de conexão do Oracle ao computador com o banco de dados Oracle que você está usando.</span><span class="sxs-lookup"><span data-stu-id="9a9a5-106">Enter the Oracle connect string to the computer with the Oracle database you are using.</span></span> <span data-ttu-id="9a9a5-107">A cadeia de conexão é gravada de um dos seguintes modos:</span><span class="sxs-lookup"><span data-stu-id="9a9a5-107">The connect string is written in one of the following ways:</span></span>  
  
 `host[:port][/service name]`  
  
 <span data-ttu-id="9a9a5-108">A cadeia de conexão também pode especificar um descritor de conexão do Oracle Net, por exemplo, `(DESCRIPTION=(ADDRESS=(PROTOCOL=tcp) (HOST=erp.contoso.com) (PORT=1521)) (CONNECT_DATA=(SERVICE_NAME=orcl)))`</span><span class="sxs-lookup"><span data-stu-id="9a9a5-108">The connection string can also specify an Oracle Net connect descriptor, for example, `(DESCRIPTION=(ADDRESS=(PROTOCOL=tcp) (HOST=erp.contoso.com) (PORT=1521)) (CONNECT_DATA=(SERVICE_NAME=orcl)))`</span></span>  
  
 <span data-ttu-id="9a9a5-109">Se estiver usando um servidor de diretório ou tnsnames, a cadeia de conexão pode ser o nome da conexão.</span><span class="sxs-lookup"><span data-stu-id="9a9a5-109">If using a directory server or tnsnames, the connect string can be the name of the connection.</span></span>  
  
 <span data-ttu-id="9a9a5-110">**Autenticação de mineração de logs da Oracle**</span><span class="sxs-lookup"><span data-stu-id="9a9a5-110">**Oracle Log Mining Authentication**</span></span>  
 <span data-ttu-id="9a9a5-111">Para inserir as credenciais para o usuário de banco de dados Oracle que está autorizado para mineração de logs, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="9a9a5-111">To enter the credentials for the Oracle database user that is authorized for log mining, select one of the following:</span></span>  
  
-   <span data-ttu-id="9a9a5-112">**Autenticação do Windows**: selecione isto para usar as credenciais de domínio atuais do Windows.</span><span class="sxs-lookup"><span data-stu-id="9a9a5-112">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="9a9a5-113">Você só poderá usar esta opção se o banco de dados Oracle estiver configurado para funcionar com autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="9a9a5-113">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="9a9a5-114">**Autenticação do Oracle**: se você selecionou esta opção, deve digitar o **Nome de usuário** e **Senha** para o usuário no banco de dados Oracle ao qual você está se conectando.</span><span class="sxs-lookup"><span data-stu-id="9a9a5-114">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Oracle database you are connecting to.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a9a5-115">Um usuário deve ter os privilégios a seguir concedidos no banco de dados Oracle para ser um usuário da mineração de logs.</span><span class="sxs-lookup"><span data-stu-id="9a9a5-115">A user must have the following privileges granted in the Oracle database to be a log-mining user.</span></span>  
> 
>  -   <span data-ttu-id="9a9a5-116">SELECT em \<any-captured-table></span><span class="sxs-lookup"><span data-stu-id="9a9a5-116">SELECT on \<any-captured-table></span></span>  
> -   <span data-ttu-id="9a9a5-117">SELECT ANY TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="9a9a5-117">SELECT ANY TRANSACTION</span></span>  
> -   <span data-ttu-id="9a9a5-118">EXECUTE em DBMS LOGMNR</span><span class="sxs-lookup"><span data-stu-id="9a9a5-118">EXECUTE on DBMS LOGMNR</span></span>  
> -   <span data-ttu-id="9a9a5-119">SELECT em V$LOGMNR CONTENTS</span><span class="sxs-lookup"><span data-stu-id="9a9a5-119">SELECT on V$LOGMNR CONTENTS</span></span>  
> -   <span data-ttu-id="9a9a5-120">SELECT em V$ARCHIVED LOG</span><span class="sxs-lookup"><span data-stu-id="9a9a5-120">SELECT on V$ARCHIVED LOG</span></span>  
> -   <span data-ttu-id="9a9a5-121">SELECT em V$LOG</span><span class="sxs-lookup"><span data-stu-id="9a9a5-121">SELECT on V$LOG</span></span>  
> -   <span data-ttu-id="9a9a5-122">SELECT em V$LOGFILE</span><span class="sxs-lookup"><span data-stu-id="9a9a5-122">SELECT on V$LOGFILE</span></span>  
> -   <span data-ttu-id="9a9a5-123">SELECT em V$DATABASE</span><span class="sxs-lookup"><span data-stu-id="9a9a5-123">SELECT on V$DATABASE</span></span>  
> -   <span data-ttu-id="9a9a5-124">SELECT em V$THREAD</span><span class="sxs-lookup"><span data-stu-id="9a9a5-124">SELECT on V$THREAD</span></span>  
> -   <span data-ttu-id="9a9a5-125">SELECT em ALL INDEXES</span><span class="sxs-lookup"><span data-stu-id="9a9a5-125">SELECT on ALL INDEXES</span></span>  
> -   <span data-ttu-id="9a9a5-126">SELECT em ALL OBJECTS</span><span class="sxs-lookup"><span data-stu-id="9a9a5-126">SELECT on ALL OBJECTS</span></span>  
> -   <span data-ttu-id="9a9a5-127">SELECT em DBA OBJECTS</span><span class="sxs-lookup"><span data-stu-id="9a9a5-127">SELECT on DBA OBJECTS</span></span>  
> -   <span data-ttu-id="9a9a5-128">SELECT em ALL TABLES</span><span class="sxs-lookup"><span data-stu-id="9a9a5-128">SELECT on ALL TABLES</span></span>  
> 
>  <span data-ttu-id="9a9a5-129">Se algum destes privilégios não puder ser concedido a um V$xxx, conceda a eles o V_S$xxx.</span><span class="sxs-lookup"><span data-stu-id="9a9a5-129">If any of these privileges cannot be granted to a V$xxx, then grant them to the V_S$xxx.</span></span>  
  
 <span data-ttu-id="9a9a5-130">**Testar Conexão**</span><span class="sxs-lookup"><span data-stu-id="9a9a5-130">**Test Connection**</span></span>  
 <span data-ttu-id="9a9a5-131">Clique em **Testar Conexão** para determinar se você estabeleceu uma conexão com o computador remoto que tem o banco de dados Oracle.</span><span class="sxs-lookup"><span data-stu-id="9a9a5-131">Click **Test Connection** to determine whether you established a connection with the remote computer that has the Oracle database.</span></span> <span data-ttu-id="9a9a5-132">Uma caixa de diálogo é aberta para informá-lo se a conexão teve êxito.</span><span class="sxs-lookup"><span data-stu-id="9a9a5-132">A dialog box opens to inform you whether the connection was successful.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9a9a5-133">Devido a uma problema conhecido, a conexão ao banco de dados de origem Oracle poderá falhar se o Designer do CDC não for executado como administrador.</span><span class="sxs-lookup"><span data-stu-id="9a9a5-133">Due to a known issue connection to the Oracle source database may fail if the CDC Designer is not run as an administrator.</span></span> <span data-ttu-id="9a9a5-134">Se a conexão falhar, feche e reinicie o Designer de CDC usando a opção **Executar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="9a9a5-134">If connection fails, close and restart the CDC Designer using the **Run as administrator** option.</span></span>  
  
 <span data-ttu-id="9a9a5-135">Depois de terminar de inserir informações nesta página, clique em **Avançar** para [Select Oracle Tables and Columns](select-oracle-tables-and-columns.md).</span><span class="sxs-lookup"><span data-stu-id="9a9a5-135">After you finish entering information on this page, click **Next** to [Select Oracle Tables and Columns](select-oracle-tables-and-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a9a5-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9a9a5-136">See Also</span></span>  
 <span data-ttu-id="9a9a5-137">[Como criar a instância de banco de dados de alteração do SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="9a9a5-137">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="9a9a5-138">Editar propriedades da instância</span><span class="sxs-lookup"><span data-stu-id="9a9a5-138">Edit Instance Properties</span></span>](edit-instance-properties.md)  
  
  
