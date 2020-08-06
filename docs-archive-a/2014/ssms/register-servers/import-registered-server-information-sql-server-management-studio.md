---
title: Importar informações de servidor registrado
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.importregisteredservers.f1
helpviewer_keywords:
- transferring registered server information
- Registered Servers [SQL Server], importing
- importing registered server information
ms.assetid: cc497a14-1360-4887-b70c-002f042823b6
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f2eddb3b83f73253e977316767f2b930bc8ab9ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683888"
---
# <a name="import-registered-server-information-sql-server-management-studio"></a><span data-ttu-id="31adc-102">Importar informações de servidor registrado (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="31adc-102">Import Registered Server Information (SQL Server Management Studio)</span></span>
  <span data-ttu-id="31adc-103">Este tópico descreve como importar informações do servidor registrado salvas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31adc-103">This topic describes how to import saved registered server information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="31adc-104">Ao exportar e, em seguida, importar os arquivos de servidores registrados, você poderá facilmente configurar vários computadores com os mesmos servidores em Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="31adc-104">Exporting and then importing registered server files lets you easily configure several computers with the same servers in Registered Servers.</span></span> <span data-ttu-id="31adc-105">Isso é útil ao gerenciar um grande número de servidores de computadores em diversos locais ou quando você deseja definir configurações de conexão básica para um usuário menos experiente.</span><span class="sxs-lookup"><span data-stu-id="31adc-105">This is useful when managing a large number of servers from computers in several locations, or when you want to configure basic connection settings for a less-experienced user.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31adc-106">Você não pode importar informações do servidor registradas no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] de versões anteriores ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31adc-106">You cannot import registered server information into [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-import-registered-server-information"></a><span data-ttu-id="31adc-107">Para importar informações de servidor registrado</span><span class="sxs-lookup"><span data-stu-id="31adc-107">To import registered server information</span></span>  
  
1.  <span data-ttu-id="31adc-108">Em Servidores Registrados, clique em tipo de servidor na barra de ferramentas Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="31adc-108">In Registered Servers, click the server type on the Registered Servers toolbar.</span></span> <span data-ttu-id="31adc-109">O tipo de servidor deve ser igual ao tipo de arquivo de exportação do servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="31adc-109">The server type must be the same as the registered server export file type.</span></span> <span data-ttu-id="31adc-110">Por exemplo, se você exportou informações do servidor registrado [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , deverá clicar em **SQL Server** na barra de ferramentas Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="31adc-110">For example, if you have exported [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registered server information, you must click **SQL Server** on the Registered Servers toolbar.</span></span>  
  
2.  <span data-ttu-id="31adc-111">Clique com o botão direito do mouse em um grupo de servidores e selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="31adc-111">Right-click a server group, and select **Import**.</span></span>  
  
3.  <span data-ttu-id="31adc-112">Na caixa de diálogo **Importar Servidores Registrados** , selecione os arquivos de servidores registrados a serem importados e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="31adc-112">In the **Import Registered Servers** dialog box, select the registered servers file to import, and then click **OK**.</span></span>  
  
     <span data-ttu-id="31adc-113">**Arquivo de importação**</span><span class="sxs-lookup"><span data-stu-id="31adc-113">**Import file**</span></span>  
     <span data-ttu-id="31adc-114">Digite o nome do arquivo de importação na caixa de texto ou clique no botão Procurar ( **...** ) para localizar o arquivo de importação no computador cliente.</span><span class="sxs-lookup"><span data-stu-id="31adc-114">Type the name of the import file in the text box, or click the Browse button (**...**) to locate the import file on the client computer.</span></span> <span data-ttu-id="31adc-115">Se você selecionar um arquivo existente, a informação de servidor registrado será anexada ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="31adc-115">If you select an existing file, the registered server information is appended to the file.</span></span> <span data-ttu-id="31adc-116">O arquivo de importação só pode ser um arquivo de servidor registrado exportado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="31adc-116">The import file can only be a previously exported registered server file.</span></span> <span data-ttu-id="31adc-117">Os arquivos de servidor registrado têm uma extensão .regsrvr.</span><span class="sxs-lookup"><span data-stu-id="31adc-117">Registered server files have a .regsrvr extension.</span></span>  
  
     <span data-ttu-id="31adc-118">**Selecione o grupo de servidores para o qual importar**</span><span class="sxs-lookup"><span data-stu-id="31adc-118">**Select the server group to import to**</span></span>  
     <span data-ttu-id="31adc-119">Selecione o nó raiz ou um grupo de servidores específico para o qual serão importadas as entradas do servidor registrado no arquivo.</span><span class="sxs-lookup"><span data-stu-id="31adc-119">Select the root node or a particular server group to which the registered server entries in the file will be imported.</span></span> <span data-ttu-id="31adc-120">Você pode importar todos os servidores registrados, servidores registrados em um grupo de servidores específico ou um único servidor registrado para o arquivo de exportação.</span><span class="sxs-lookup"><span data-stu-id="31adc-120">You can import all registered servers, registered servers in a particular server group, or a single registered server to the export file.</span></span> <span data-ttu-id="31adc-121">A funcionalidade de importação é recursiva; por exemplo, se o grupo de servidores A contiver o grupo de servidores B e o grupo de servidores B contiver os grupos de servidores C e D, a importação do grupo de servidores A exportará todas as entradas em A, B, C e D.</span><span class="sxs-lookup"><span data-stu-id="31adc-121">The import functionality is recursive; for example, if server group A contains server group B, and server group B contains server groups C and D, importing server group A exports all entries in A, B, C, and D.</span></span>  
  
     <span data-ttu-id="31adc-122">O grupo de servidores exibe somente os grupos da árvore atual de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="31adc-122">The server group displays only the server groups of the current registered server tree.</span></span>  
  
     <span data-ttu-id="31adc-123">Se você selecionar importar um grupo de servidores ou um servidor existente, uma mensagem confirmará que você deseja substituir o servidor ou o grupo de servidores existente.</span><span class="sxs-lookup"><span data-stu-id="31adc-123">If you select to import an existing server group or server, a message confirms that you want to overwrite the existing server or server group.</span></span>  
  
 <span data-ttu-id="31adc-124">Os registros de servidores que usam a autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] armazenam senhas por usuário.</span><span class="sxs-lookup"><span data-stu-id="31adc-124">Server registrations that use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication store passwords on a per-user basis.</span></span> <span data-ttu-id="31adc-125">Depois de importar os registros de servidores, os usuários devem digitar a senha para cada servidor quando se conectarem pela primeira vez, armazenando as senhas em suas listas de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="31adc-125">After importing the server registrations, users must enter the password for each server the first time they connect, storing the passwords in their lists of registered servers.</span></span> <span data-ttu-id="31adc-126">Isso não é necessário para servidores registrados por meio da autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="31adc-126">This is not necessary for servers registered through Windows Authentication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31adc-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="31adc-127">See Also</span></span>  
 <span data-ttu-id="31adc-128">[Alterar o registro de um servidor &#40;SQL Server Management Studio&#41;](change-a-server-s-registration-sql-server-management-studio.md) [exportar informações do servidor registrado &#40;SQL Server Management Studio&#41;](export-registered-server-information-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="31adc-128">[Change a Server's Registration &#40;SQL Server Management Studio&#41;](change-a-server-s-registration-sql-server-management-studio.md) [Export Registered Server Information &#40;SQL Server Management Studio&#41;](export-registered-server-information-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="31adc-129">Criar um novo servidor registrado &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="31adc-129">Create a New Registered Server &#40;SQL Server Management Studio&#41;</span></span>](create-a-new-registered-server-sql-server-management-studio.md)  
  
  
