---
title: Exportar informações de servidor registrado
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.exportregisteredservers.f1
helpviewer_keywords:
- Registered Servers [SQL Server], exporting
- exporting registered server information
- transferring registered server information
ms.assetid: b65e168f-b6bf-489c-b8ad-3b8644acf0b6
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 03092de2d722e8f8b807dbb3d23c4b4e2b91f6f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683887"
---
# <a name="export-registered-server-information-sql-server-management-studio"></a><span data-ttu-id="b8db8-102">Exportar informações de servidor registrado (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b8db8-102">Export Registered Server Information (SQL Server Management Studio)</span></span>
  <span data-ttu-id="b8db8-103">Este tópico descreve como salvar e exportar informações de servidor registrado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]e distribuí-las para outros empregados ou servidores.</span><span class="sxs-lookup"><span data-stu-id="b8db8-103">This topic describes how to save and export registered server information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]and distribute it to other employees or servers.</span></span> <span data-ttu-id="b8db8-104">É possível usar esse recurso de exportação para apresentar uma interface com o usuário consistente em computadores múltiplos.</span><span class="sxs-lookup"><span data-stu-id="b8db8-104">You can use this export feature to present a consistent user interface on multiple computers.</span></span>  
  
 <span data-ttu-id="b8db8-105">Exportar e, depois, importar os arquivos de Servidores Registrados permite que você configure facilmente vários computadores com os mesmos servidores em Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="b8db8-105">Exporting and then importing Registered Server files lets you easily configure several computers with the same servers in Registered Servers.</span></span> <span data-ttu-id="b8db8-106">Isso é útil quando se gerencia um grande número de servidores de computadores em diversos locais ou quando você deseja configurar um usuário menos experiente com configurações de conexão básica.</span><span class="sxs-lookup"><span data-stu-id="b8db8-106">This is useful when managing a large number of servers from computers in several locations, or when you want to configure a less experienced user with basic connection settings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b8db8-107">Os registros de servidores que usam a autenticação do SQL Server armazenam senhas por usuário.</span><span class="sxs-lookup"><span data-stu-id="b8db8-107">Server registrations that use SQL Server Authentication store passwords on a per-user basis.</span></span> <span data-ttu-id="b8db8-108">Depois de exportar e importar os registros de servidores, os usuários devem digitar a senha para cada servidor quando se conectarem pela primeira vez, armazenando as senhas em suas listas de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="b8db8-108">After exporting and importing the server registrations, users must enter the password for each server the first time they connect, storing the passwords in their lists of registered servers.</span></span> <span data-ttu-id="b8db8-109">Isso não é necessário para servidores registrados que usam a autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="b8db8-109">This is not necessary for servers registered using Windows Authentication.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-export-registered-server-information"></a><span data-ttu-id="b8db8-110">Para exportar informações de servidor registrado</span><span class="sxs-lookup"><span data-stu-id="b8db8-110">To export registered server information</span></span>  
  
1.  <span data-ttu-id="b8db8-111">Em Servidores Registrados, clique com o botão direito do mouse em um grupo de servidores e clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="b8db8-111">In Registered Servers, right-click a server group, and then click **Export**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b8db8-112">Você pode exportar um servidor individual, toda a árvore de servidores registrados ou um subconjunto da árvore de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="b8db8-112">You can export an individual server, all of the registered server tree, or a subset of the registered server tree.</span></span>  
  
2.  <span data-ttu-id="b8db8-113">Na caixa de diálogo **Exportar Servidores Registrados** , faça as seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="b8db8-113">In the **Export Registered Servers** dialog box, make the following selections.</span></span>  
  
     <span data-ttu-id="b8db8-114">**Grupo de servidor**</span><span class="sxs-lookup"><span data-stu-id="b8db8-114">**Server group**</span></span>  
     <span data-ttu-id="b8db8-115">Especifique o grupo de servidor que será exportado.</span><span class="sxs-lookup"><span data-stu-id="b8db8-115">Specify the server group which will be exported.</span></span> <span data-ttu-id="b8db8-116">Exporte todos os servidores registrados, servidores registrados em um grupo de servidores específicos ou um único servidor registrado para o arquivo de exportação.</span><span class="sxs-lookup"><span data-stu-id="b8db8-116">Export all registered servers, registered servers in a particular server group, or a single registered server to the export file.</span></span> <span data-ttu-id="b8db8-117">A funcionalidade de exportação é recursiva; por exemplo, se o grupo de servidores A contiver o grupo de servidores B, e o grupo de servidores B contiver os grupos de servidores C e D, a exportação do grupo de servidores A exportará todas as entradas em A, B, C e D.</span><span class="sxs-lookup"><span data-stu-id="b8db8-117">The export functionality is recursive; for example, if server group A contains server group B, and server group B contains server groups C and D, exporting server group A exports all entries in A, B, C, and D.</span></span>  
  
     <span data-ttu-id="b8db8-118">O grupo de servidores exibe somente os grupos da árvore atual de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="b8db8-118">The server group displays only the server groups of the current registered server tree.</span></span>  
  
     <span data-ttu-id="b8db8-119">**Arquivo de exportação**</span><span class="sxs-lookup"><span data-stu-id="b8db8-119">**Export file**</span></span>  
     <span data-ttu-id="b8db8-120">Digite o nome do arquivo de exportação na caixa de texto ou use o botão Procurar ( **...** ) para localizar um arquivo de exportação no computador cliente.</span><span class="sxs-lookup"><span data-stu-id="b8db8-120">Type the name of the export file in the text box or use the Browse button (**...**) to locate an export file on the client computer.</span></span> <span data-ttu-id="b8db8-121">Se você selecionar um arquivo existente, a informação de servidor registrado será anexada ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="b8db8-121">If you select an existing file, the registered server information is appended to the file.</span></span> <span data-ttu-id="b8db8-122">Use a extensão .regsrvr.</span><span class="sxs-lookup"><span data-stu-id="b8db8-122">Use the .regsrvr extension.</span></span> <span data-ttu-id="b8db8-123">Se você quiser que as informações do servidor registrado estejam disponíveis para outros usuários ou outro computador, você poderá salvar o arquivo na rede.</span><span class="sxs-lookup"><span data-stu-id="b8db8-123">If you want your registered server information to be available to other users or another computer, you can save the file on the network.</span></span> <span data-ttu-id="b8db8-124">Outros usuários podem acessar o arquivo e podem importar parte ou todas as informações do servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="b8db8-124">Other users can access the file and import part or all of the registered server information.</span></span> <span data-ttu-id="b8db8-125">Se você selecionar um arquivo existente como o arquivo de exportação, o conteúdo do arquivo será substituído pelas informações de registro do servidor.</span><span class="sxs-lookup"><span data-stu-id="b8db8-125">If you select an existing file as your export file, the contents of the file are overwritten with the server registration information.</span></span>  
  
     <span data-ttu-id="b8db8-126">**Não inclua nomes de usuário e senhas no arquivo de exportação**</span><span class="sxs-lookup"><span data-stu-id="b8db8-126">**Do not include user names and passwords in the export file**</span></span>  
     <span data-ttu-id="b8db8-127">Exclua nomes de usuário ao exportar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="b8db8-127">Exclude user names when exporting the file.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b8db8-128">Embora os arquivos de exportação sejam criptografados, se nomes de usuários e senhas da autenticação do SQL Server forem incluídas no arquivo, o acesso ao arquivo deve ser cuidadosamente controlado.</span><span class="sxs-lookup"><span data-stu-id="b8db8-128">Although the export files are encrypted, if user names and SQL Server Authentication passwords are included in the file, access to the file should be carefully controlled.</span></span> <span data-ttu-id="b8db8-129">Portanto, os nomes de usuários e senhas são excluídos do arquivo de exportação por padrão.</span><span class="sxs-lookup"><span data-stu-id="b8db8-129">User names and passwords are therefore excluded from the export file by default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8db8-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b8db8-130">See Also</span></span>  
 <span data-ttu-id="b8db8-131">[Importar informações do servidor registrado &#40;SQL Server Management Studio&#41;](import-registered-server-information-sql-server-management-studio.md) [criar um novo servidor registrado &#40;SQL Server Management Studio](create-a-new-registered-server-sql-server-management-studio.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="b8db8-131">[Import Registered Server Information &#40;SQL Server Management Studio&#41;](import-registered-server-information-sql-server-management-studio.md) [Create a New Registered Server &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md)</span></span>  
  
  
