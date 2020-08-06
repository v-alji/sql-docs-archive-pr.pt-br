---
title: 'Ferramenta de gerenciamento de linha de comando: SqlLocalDB.exe | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_location:
- sqluserinstance.dll
ms.assetid: dd0882b1-a8a9-447a-8bdf-0f9d7f36d336
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d21a6a8879e981e52bd2e7d3bd05a37e65d8cf4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570031"
---
# <a name="command-line-management-tool-sqllocaldbexe"></a><span data-ttu-id="73bfa-102">Ferramenta de gerenciamento da linha de comando: SqlLocalDB.exe</span><span class="sxs-lookup"><span data-stu-id="73bfa-102">Command-Line Management Tool: SqlLocalDB.exe</span></span>
  <span data-ttu-id="73bfa-103">O SqlLocalDB.exe é uma ferramenta simples que permite ao usuário a gerenciar facilmente as instâncias de LocalDB na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="73bfa-103">SqlLocalDB.exe is a simple tool that enables the user to easily manage LocalDB instances from the command line.</span></span> <span data-ttu-id="73bfa-104">É implementado como um wrapper simples com base na instância da API de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="73bfa-104">It is implemented as a simple wrapper around the LocalDB instance API.</span></span> <span data-ttu-id="73bfa-105">Assim como ocorre em muitas ferramentas semelhantes do SQL Server (por exemplo, SQLCMD), os parâmetros são passados para SqlLocalDB como argumentos de linha de comando e a saída é enviada ao console.</span><span class="sxs-lookup"><span data-stu-id="73bfa-105">As in many similar SQL Server tools (for example, SQLCMD), parameters are passed to SqlLocalDB as command-line arguments and output is sent to the console.</span></span>  
  
 <span data-ttu-id="73bfa-106">O SqlLocalDB permite que os desenvolvedores utilizem o LocalDB sem precisar escrever o código para chamar a API ou depender de outras ferramentas para fazer isso para eles.</span><span class="sxs-lookup"><span data-stu-id="73bfa-106">SqlLocalDB enables developers to use LocalDB without having to write code to call the API or depend on other tools to do it for them.</span></span>  
  
## <a name="sqllocaldb-options"></a><span data-ttu-id="73bfa-107">Opções de SqlLocalDB</span><span class="sxs-lookup"><span data-stu-id="73bfa-107">SqlLocalDB Options</span></span>  
 <span data-ttu-id="73bfa-108">O SqlLocalDB oferece suporte para as seguintes opções.</span><span class="sxs-lookup"><span data-stu-id="73bfa-108">SqlLocalDB supports the following options.</span></span>  
  
|<span data-ttu-id="73bfa-109">Opção</span><span class="sxs-lookup"><span data-stu-id="73bfa-109">Option</span></span>|<span data-ttu-id="73bfa-110">O que faz</span><span class="sxs-lookup"><span data-stu-id="73bfa-110">What it does</span></span>|  
|------------|------------------|  
|`-?`|<span data-ttu-id="73bfa-111">Imprime o texto da Ajuda.</span><span class="sxs-lookup"><span data-stu-id="73bfa-111">Prints help text.</span></span>|  
|`create&#124;c "instance name" [version-number] [-s]`|<span data-ttu-id="73bfa-112">Cria uma nova instância de LocalDB com um nome e uma versão especificados.</span><span class="sxs-lookup"><span data-stu-id="73bfa-112">Creates a new LocalDB instance with a specified name and version.</span></span><br /><br /> <span data-ttu-id="73bfa-113">Se o parâmetro [version-number] for omitido, o valor padrão será a versão de compilação do SqlLocalDB.</span><span class="sxs-lookup"><span data-stu-id="73bfa-113">If the [version-number] parameter is omitted, it defaults to the SqlLocalDB build version.</span></span><br /><br /> <span data-ttu-id="73bfa-114">- s inicia a nova instância de LocalDB depois que ela é criada.</span><span class="sxs-lookup"><span data-stu-id="73bfa-114">-s starts the new LocalDB instance after it is created.</span></span>|  
|`delete&#124;d "instance name"`|<span data-ttu-id="73bfa-115">Excluir a instância de LocalDB com o nome especificado.</span><span class="sxs-lookup"><span data-stu-id="73bfa-115">Deletes the LocalDB instance with the specified name.</span></span>|  
|`start&#124;s "instance name"`|<span data-ttu-id="73bfa-116">Inicia a instância de LocalDB com o nome especificado.</span><span class="sxs-lookup"><span data-stu-id="73bfa-116">Starts the LocalDB instance with the specified name.</span></span>|  
|`stop&#124;p "instance name" [-i&#124;-k]`|<span data-ttu-id="73bfa-117">Interrompe a instância de LocalDB com o nome especificado, depois que a execução das consultas atuais são concluídas.</span><span class="sxs-lookup"><span data-stu-id="73bfa-117">Stops the LocalDB instance with the specified name, after current queries finish running.</span></span><br /><br /> <span data-ttu-id="73bfa-118">-i solicita o desligamento da instância de LocalDB com a opção NOWAIT.</span><span class="sxs-lookup"><span data-stu-id="73bfa-118">-i requests the LocalDB instance shutdown with the NOWAIT option.</span></span><br /><br /> <span data-ttu-id="73bfa-119">-k elimina o processo da instância de LocalDB sem contatá-la.</span><span class="sxs-lookup"><span data-stu-id="73bfa-119">-k kills the LocalDB instance process without contacting it.</span></span>|  
|`share&#124;h ["owner SID or account"] "private name" "shared name"`|<span data-ttu-id="73bfa-120">Compartilha a instância privada especificada que usa o nome compartilhado especificado.</span><span class="sxs-lookup"><span data-stu-id="73bfa-120">Shares the specified private instance using the specified shared name.</span></span> <span data-ttu-id="73bfa-121">Se a SID ou o nome de conta do usuário for omitido, o valor padrão será o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="73bfa-121">If the user SID or account name is omitted, it defaults to the current user.</span></span>|  
|`unshare&#124;u "shared name"`|<span data-ttu-id="73bfa-122">Descompartilha a instância de LocalDB especificada.</span><span class="sxs-lookup"><span data-stu-id="73bfa-122">Unshares the specified shared LocalDB instance.</span></span>|  
|`info&#124;i`|<span data-ttu-id="73bfa-123">Lista todas as instâncias de LocalDB existentes pertencentes ao usuário atual e todas as instâncias de LocalDB compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="73bfa-123">Lists all existing LocalDB instances that are owned by the current user and all shared LocalDB instances.</span></span>|  
|`info&#124;i "instance name"`|<span data-ttu-id="73bfa-124">Imprime as informações sobre a instância de LocalDB especificada.</span><span class="sxs-lookup"><span data-stu-id="73bfa-124">Prints the information about the specified LocalDB instance.</span></span>|  
|`versions&#124;v`|<span data-ttu-id="73bfa-125">Lista todas as versões de LocalDB instaladas no computador.</span><span class="sxs-lookup"><span data-stu-id="73bfa-125">Lists all LocalDB versions installed on the computer.</span></span>|  
|||  
|`trace&#124;t on&#124;off`|<span data-ttu-id="73bfa-126">Ativa e desativa o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="73bfa-126">Turns tracing on and off.</span></span>|  
  
 <span data-ttu-id="73bfa-127">O SqlLocalDB trata os espaços como delimitadores; você deve delimitar os nomes de instância que contêm espaços e caracteres especiais com aspas.</span><span class="sxs-lookup"><span data-stu-id="73bfa-127">SqlLocalDB treats spaces as delimiters; you must surround the instance names that contain spaces and special characters with quotes.</span></span> <span data-ttu-id="73bfa-128">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="73bfa-128">For example:</span></span>  
  
 `SqlLocalDB create "My instance name with spaces"`  
  
  
