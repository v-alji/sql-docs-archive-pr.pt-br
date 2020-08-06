---
title: Gerenciador de Conexões SMO | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], SMO
- SMO connection manager
- connection managers [Integration Services], SMO
ms.assetid: d273f1fb-a6a8-4f2f-a5ff-55c2e3de4723
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 988eef214608399bc3ec483d9976c2f5d52acb2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685241"
---
# <a name="smo-connection-manager"></a><span data-ttu-id="06ff1-102">gerenciador de conexões SMO</span><span class="sxs-lookup"><span data-stu-id="06ff1-102">SMO Connection Manager</span></span>
  <span data-ttu-id="06ff1-103">Um gerenciador de conexões SMO habilita um pacote para conexão a um servidor do SQL Management Object (SMO).</span><span class="sxs-lookup"><span data-stu-id="06ff1-103">An SMO connection manager enables a package to connect to a SQL Management Object (SMO) server.</span></span> <span data-ttu-id="06ff1-104">As tarefas de transferência que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] inclui usam um gerenciador de conexões do SMO.</span><span class="sxs-lookup"><span data-stu-id="06ff1-104">The transfer tasks that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes use an SMO connection manager.</span></span> <span data-ttu-id="06ff1-105">Por exemplo, a tarefa Transferir Logons que transfere os logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa um gerenciador de conexões do SMO.</span><span class="sxs-lookup"><span data-stu-id="06ff1-105">For example, the Transfer Logins task that transfers [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins uses an SMO connection manager.</span></span>  
  
 <span data-ttu-id="06ff1-106">Quando você adiciona um gerenciador de conexões SMO a um pacote, o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] cria um gerenciador de conexões que disponibilizará uma conexão do SMO no momento da execução, define as propriedades do gerenciador de conexões e adiciona o gerenciador de conexões à coleção do `Connections` no pacote.</span><span class="sxs-lookup"><span data-stu-id="06ff1-106">When you add an SMO connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an SMO connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="06ff1-107">A propriedade `ConnectionManagerType` do gerenciador de conexões é definida como `SMOServer`.</span><span class="sxs-lookup"><span data-stu-id="06ff1-107">The `ConnectionManagerType` property of the connection manager is set to `SMOServer`.</span></span>  
  
 <span data-ttu-id="06ff1-108">Você pode configurar um gerenciador de conexões SMO das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="06ff1-108">You can configure an SMO connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="06ff1-109">Especifique o nome de um servidor no qual o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está instalado.</span><span class="sxs-lookup"><span data-stu-id="06ff1-109">Specify the name of a server on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
-   <span data-ttu-id="06ff1-110">Selecione o modo de autenticação para a conexão com o servidor.</span><span class="sxs-lookup"><span data-stu-id="06ff1-110">Select the authentication mode for connecting to the server.</span></span>  
  
## <a name="configuration-of-the-smo-connection-manager"></a><span data-ttu-id="06ff1-111">Configuração do gerenciador de conexões SMO</span><span class="sxs-lookup"><span data-stu-id="06ff1-111">Configuration of the SMO Connection Manager</span></span>  
 <span data-ttu-id="06ff1-112">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="06ff1-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="06ff1-113">Para obter mais informações sobre as propriedades que podem ser definidas no Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consulte [Editor do Gerenciador de Conexões do SMO](../smo-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="06ff1-113">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [SMO Connection Manager Editor](../smo-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="06ff1-114">Para obter informações sobre como configurar um gerenciador de conexões programaticamente, consulte <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Adicionando conexões programaticamente](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="06ff1-114">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ff1-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="06ff1-115">See Also</span></span>  
 [<span data-ttu-id="06ff1-116">Conexões do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="06ff1-116">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
