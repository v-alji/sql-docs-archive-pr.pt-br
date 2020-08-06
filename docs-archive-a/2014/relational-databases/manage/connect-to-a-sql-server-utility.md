---
title: Conectar a um Utilitário do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: b9b90b8d-241f-4b74-ac14-de7b10ea1821
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e8e59a28e083fc302faebbcba932c18a04e73a7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570690"
---
# <a name="connect-to-a-sql-server-utility"></a><span data-ttu-id="90823-102">Conectar a um Utilitário do SQL Server</span><span class="sxs-lookup"><span data-stu-id="90823-102">Connect to a SQL Server Utility</span></span>
  <span data-ttu-id="90823-103">Para que você possa se conectar a um Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , é necessário criar um UCP (ponto de controle do utilitário).</span><span class="sxs-lookup"><span data-stu-id="90823-103">Before you can connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, you must create a utility control point (UCP).</span></span> <span data-ttu-id="90823-104">Para obter mais informações, consulte [Recursos e tarefas do utilitário do SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="90823-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>

 <span data-ttu-id="90823-105">Para exibir e gerenciar a integridade de recurso do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (SSMS) para conectar-se a um Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="90823-105">To view and manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource health, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (SSMS) to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>

 <span data-ttu-id="90823-106">Para conectar-se a um Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio do SSMS:</span><span class="sxs-lookup"><span data-stu-id="90823-106">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility through SSMS:</span></span>

1.  <span data-ttu-id="90823-107">Inicie o SSMS.</span><span class="sxs-lookup"><span data-stu-id="90823-107">Launch SSMS.</span></span>

2.  <span data-ttu-id="90823-108">No SSMS, conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90823-108">In SSMS, connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>

3.  <span data-ttu-id="90823-109">Clique em **Exibir** e em **Gerenciador do Utilitário**.</span><span class="sxs-lookup"><span data-stu-id="90823-109">Click **View** and then **Utility Explorer**.</span></span>

4.  <span data-ttu-id="90823-110">No painel de navegação do Gerenciador do Utilitário, clique em ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Conectar ao Utilitário**.</span><span class="sxs-lookup"><span data-stu-id="90823-110">In the Utility Explorer navigation pane, click ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Connect to Utility**.</span></span>

5.  <span data-ttu-id="90823-111">Na caixa de diálogo **Conectar ao Servidor** , especifique o nome da instância UCP e depois clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="90823-111">In the **Connect to Server** dialog box, specify the UCP instance name, then click **Connect**.</span></span>

6.  <span data-ttu-id="90823-112">Exiba o painel de navegação do Gerenciador do Utilitário para ver um modo de exibição de árvore dos recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no UCP.</span><span class="sxs-lookup"><span data-stu-id="90823-112">View the Utility Explorer Navigation Pane to see a tree view of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources in the UCP.</span></span>

 <span data-ttu-id="90823-113">Criar um novo UCP também conecta ao Utilitário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="90823-113">Creating a new UCP also connects you to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="90823-114">Para obter mais informações, veja [Criar um ponto de controle do Utilitário do SQL Server &#40;Utilitário do SQL Server&#41;](create-a-sql-server-utility-control-point-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="90823-114">For more information, see [Create a SQL Server Utility Control Point &#40;SQL Server Utility&#41;](create-a-sql-server-utility-control-point-sql-server-utility.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="90823-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="90823-115">See Also</span></span>
 <span data-ttu-id="90823-116">[Utilitário do SQL Server recursos e tarefas](sql-server-utility-features-and-tasks.md) [Exibir Resource Health resultados da política &#40;utilitário do SQL Server&#41;](view-resource-health-policy-results-sql-server-utility.md)</span><span class="sxs-lookup"><span data-stu-id="90823-116">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) [View Resource Health Policy Results &#40;SQL Server Utility&#41;](view-resource-health-policy-results-sql-server-utility.md)</span></span>


