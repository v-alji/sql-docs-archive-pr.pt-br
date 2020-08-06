---
title: Conectar ao Servidor (página Parâmetros Adicionais de Conexão) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttoserver.options.registeredservers.f1
ms.assetid: ba34b01a-6289-4eb8-8341-fa3d9ec87b3f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5c6a23df6a6b9ea324d54fd270f5aa2269471ed8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583819"
---
# <a name="connect-to-server-additional-connection-parameters-page"></a><span data-ttu-id="d637d-102">Conectar ao Servidor (página Parâmetros Adicionais de Conexão)</span><span class="sxs-lookup"><span data-stu-id="d637d-102">Connect to Server (Additional Connection Parameters Page)</span></span>
  <span data-ttu-id="d637d-103">A caixa de diálogo **Conectar a** do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] apresenta os valores de cadeia de conexão mais comuns como opções.</span><span class="sxs-lookup"><span data-stu-id="d637d-103">The **Connect to** dialog box of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] presents the most common connection string values as options.</span></span> <span data-ttu-id="d637d-104">Use a página **Parâmetros Adicionais de Conexão** para acrescentar mais parâmetros de conexão à cadeia de conexões.</span><span class="sxs-lookup"><span data-stu-id="d637d-104">Use the **Additional Connection Parameters** page to add more connection parameters to the connection string.</span></span>  
  
-   <span data-ttu-id="d637d-105">Os parâmetros adicionais de conexão podem ser quaisquer parâmetro de conexão ODBC.</span><span class="sxs-lookup"><span data-stu-id="d637d-105">Additional connection parameters can be any ODBC connection parameter.</span></span>  
  
-   <span data-ttu-id="d637d-106">Parâmetros adicionais de conexão devem ser adicionados no formato **;parameter1=value1;parameter2=value2**.</span><span class="sxs-lookup"><span data-stu-id="d637d-106">Additional connection parameters should be added in the format **;parameter1=value1;parameter2=value2**.</span></span>  
  
-   <span data-ttu-id="d637d-107">Parâmetros adicionados através da página **Parâmetros de Conexão Adicionais** são adicionados aos parâmetros selecionados usando as opções da caixa de diálogo **Conectar a** .</span><span class="sxs-lookup"><span data-stu-id="d637d-107">Parameters added using the **Additional Connection Parameters** page are added to the parameters selected using the **Connect to** dialog box options.</span></span>  
  
-   <span data-ttu-id="d637d-108">A última instância fornecida de cada parâmetro anula qualquer instância anterior do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d637d-108">The last instance of each parameter provided overrides any previous instances of the parameter.</span></span> <span data-ttu-id="d637d-109">Parâmetros adicionados usando a página **Parâmetros de Conexão Adicionais** seguem e substituem os parâmetros fornecidos nas guias **Logon** ou **Propriedades da Conexão** .</span><span class="sxs-lookup"><span data-stu-id="d637d-109">Parameters added using the **Additional Connection Parameters** page follow and replace the parameters provided in the **Login** or **Connection Properties** tabs.</span></span> <span data-ttu-id="d637d-110">Por exemplo, se a guia **Logon** fornecer **SERVER1** como o **Nome do servidor**e a página **Parâmetros de Conexão Adicionais** contiver **;SERVER=SERVER2**, a conexão será feita com o **SERVER2**.</span><span class="sxs-lookup"><span data-stu-id="d637d-110">For example, if the **Login** tab provides **SERVER1** as the **Server name**, and the **Additional Connection Parameters** page contains **;SERVER=SERVER2**, the connection will be made to **SERVER2**.</span></span>  
  
-   <span data-ttu-id="d637d-111">Parâmetros adicionados usando a página **Parâmetros de Conexão Adicionais** sempre são transmitidos como texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="d637d-111">Parameters added using the **Additional Connection Parameters** page are always passed as plain text.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="d637d-112">Não inclua credenciais de logon e senhas na guia **Parâmetros de Conexão Adicionais** .</span><span class="sxs-lookup"><span data-stu-id="d637d-112">Do not include login credentials and passwords in the **Additional Connection Parameters** page.</span></span> <span data-ttu-id="d637d-113">Eles não serão criptografados quando forem transmitidos pela rede.</span><span class="sxs-lookup"><span data-stu-id="d637d-113">They will not be encrypted when they are passed across the network.</span></span> <span data-ttu-id="d637d-114">Use a guia **Logon** em vez disso.</span><span class="sxs-lookup"><span data-stu-id="d637d-114">Use the **Login** tab instead.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="d637d-115">Lista de Tarefas</span><span class="sxs-lookup"><span data-stu-id="d637d-115">Task List</span></span>  
  
### <a name="to-show-the-additional-connection-parameters-page"></a><span data-ttu-id="d637d-116">Para exibir a página Parâmetros Adicionais de Conexão</span><span class="sxs-lookup"><span data-stu-id="d637d-116">To show the Additional Connection Parameters page</span></span>  
  
1.  <span data-ttu-id="d637d-117">No [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], no menu **Consulta** , aponte a **Conexão**e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="d637d-117">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], on the **Query** menu, point to **Connection**, and then click **Connect**.</span></span>  
  
2.  <span data-ttu-id="d637d-118">Na caixa de diálogo **Conectar a** , clique em **Opções**e depois clique na guia **Parâmetros de Conexão Adicionais** .</span><span class="sxs-lookup"><span data-stu-id="d637d-118">In the **Connect to** dialog box, click **Options**, and then click the **Additional Connection Parameters** tab.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d637d-119">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d637d-119">Examples</span></span>  
  
### <a name="example-a-connecting-to-the-database-engine"></a><span data-ttu-id="d637d-120">Exemplo A: Conectando ao Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="d637d-120">Example A: Connecting to the Database Engine</span></span>  
 <span data-ttu-id="d637d-121">Para conectar ao banco de dados do [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] em um servidor nomeado CONTABILIDADE, digite o seguinte na página **Parâmetros de conexão adicionais** :</span><span class="sxs-lookup"><span data-stu-id="d637d-121">To connect to the [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] database on a server named ACCOUNTING, enter the following in the **Additional connection parameters** page:</span></span>  
  
```  
;SERVER=ACCOUNTING;DATABASE=AdventureWorks2012  
```  
  
### <a name="example-b-connecting-to-analysis-services"></a><span data-ttu-id="d637d-122">Exemplo B: Conectando a Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d637d-122">Example B: Connecting to Analysis Services</span></span>  
 <span data-ttu-id="d637d-123">Para conectar aos servidores de análises e fazer todas as partições escutarem as notificações a serem consultadas em tempo real (ignorando o cache) e para definir o valor do tempo limite de write-back como 5, digite o seguinte na página **Parâmetros de conexão adicionais** :</span><span class="sxs-lookup"><span data-stu-id="d637d-123">To connect to the Analysis Servers and cause all the partitions listening for notifications to be queried as real time (bypassing caching), and to set the writeback time out value to 5, enter the following in the **Additional connection parameters** page:</span></span>  
  
```  
;Real Time Olap=TRUE;Writeback Timeout=5  
```  
  
  
