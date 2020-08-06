---
title: Opção de reprodução (ferramenta de administração do Distributed Replay) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: d7bce6a5-d414-488d-a3cd-50c1c62019c4
author: stevestein
ms.author: sstein
ms.openlocfilehash: a3114d7c2a2a7908e4e010fbf5d80c7d332d264c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684960"
---
# <a name="replay-option-distributed-replay-administration-tool"></a><span data-ttu-id="b6b55-102">Opção Replay (ferramenta de administração do Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="b6b55-102">Replay Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="b6b55-103">A [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ferramenta de administração de Distributed Replay, `DReplay.exe` , é uma ferramenta de linha de comando que você pode usar para se comunicar com o Distributed Replay Controller.</span><span class="sxs-lookup"><span data-stu-id="b6b55-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="b6b55-104">Este tópico descreve a opção de linha de comando **replay** e a sintaxe correspondente.</span><span class="sxs-lookup"><span data-stu-id="b6b55-104">This topic describes the **replay** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="b6b55-105">A opção **replay** inicia o estágio de reprodução de eventos, no qual o controlador despacha dados de reprodução aos clientes especificados, inicia a reprodução distribuída e sincroniza os clientes.</span><span class="sxs-lookup"><span data-stu-id="b6b55-105">The **replay** option initiates the event replay stage, in which the controller dispatches replay data to the specified clients, launches the distributed replay and synchronizes the clients.</span></span> <span data-ttu-id="b6b55-106">Opcionalmente, cada cliente que participa da reprodução pode gravar a atividade de reprodução e salvar um arquivo de rastreamento de resultado localmente.</span><span class="sxs-lookup"><span data-stu-id="b6b55-106">Optionally, each client participating in the replay can record the replay activity and save a result trace file locally.</span></span>

 <span data-ttu-id="b6b55-107">![Ícone de link do tópico](../../database-engine/media/topic-link.gif "Ícone de link do tópico") Para obter mais informações sobre as convenções de sintaxe usadas com a sintaxe da ferramenta de administração, confira [Convenções de sintaxe Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b6b55-107">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="b6b55-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b6b55-108">Syntax</span></span>

```

      dreplay replay [-mcontroller] -dcontroller_working_dir [-o]
    [-starget_server] -wclients [-cconfig_file]
    [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="b6b55-109">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b6b55-109">Parameters</span></span>
 <span data-ttu-id="b6b55-110">**-m** *Controller* especifica o nome do computador do controlador.</span><span class="sxs-lookup"><span data-stu-id="b6b55-110">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="b6b55-111">Você pode usar "`localhost`" ou "`.`" para fazer referência ao computador local.</span><span class="sxs-lookup"><span data-stu-id="b6b55-111">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="b6b55-112">Se o parâmetro **-m** não for especificado, será usado o computador local.</span><span class="sxs-lookup"><span data-stu-id="b6b55-112">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="b6b55-113">**-d** *controller_working_dir* especifica o diretório no controlador em que o arquivo intermediário será armazenado.</span><span class="sxs-lookup"><span data-stu-id="b6b55-113">**-d** *controller_working_dir* Specifies the directory on the controller where the intermediate file will be stored.</span></span> <span data-ttu-id="b6b55-114">O parâmetro **-d** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="b6b55-114">The **-d** parameter is required.</span></span>

 <span data-ttu-id="b6b55-115">Os seguintes requisitos são aplicados:</span><span class="sxs-lookup"><span data-stu-id="b6b55-115">The following requirements apply:</span></span>

-   <span data-ttu-id="b6b55-116">O diretório deve residir no controlador.</span><span class="sxs-lookup"><span data-stu-id="b6b55-116">The directory must reside on the controller.</span></span>

-   <span data-ttu-id="b6b55-117">Você deve especificar o caminho completo, iniciando com uma letra da unidade (por exemplo, `c:\WorkingDir`).</span><span class="sxs-lookup"><span data-stu-id="b6b55-117">You must specify the full path, starting with a drive letter (for example, `c:\WorkingDir`).</span></span>

-   <span data-ttu-id="b6b55-118">O caminho não deve terminar com uma barra invertida "`\`".</span><span class="sxs-lookup"><span data-stu-id="b6b55-118">The path must not end with a backslash "`\`".</span></span>

-   <span data-ttu-id="b6b55-119">Não há suporte para caminhos UNC.</span><span class="sxs-lookup"><span data-stu-id="b6b55-119">UNC paths are not supported.</span></span>

 <span data-ttu-id="b6b55-120">**-o** Captura a atividade de reprodução dos clientes e salva-o em um arquivo de rastreamento de resultado no caminho especificado pelo `<ResultDirectory>` elemento no arquivo de configuração do cliente, `DReplayClient.xml` .</span><span class="sxs-lookup"><span data-stu-id="b6b55-120">**-o** Captures the clients' replay activity and saves it to a result trace file in the path specified by the `<ResultDirectory>` element in the client configuration file, `DReplayClient.xml`.</span></span>

 <span data-ttu-id="b6b55-121">Quando o parâmetro **-o** não é especificado, o arquivo de rastreamento de resultado não é gerado.</span><span class="sxs-lookup"><span data-stu-id="b6b55-121">When the **-o** parameter is not specified, the result trace file is not generated.</span></span> <span data-ttu-id="b6b55-122">A saída do console retorna informações resumidas ao término da reprodução, mas nenhuma outra estatística de reprodução está disponível.</span><span class="sxs-lookup"><span data-stu-id="b6b55-122">The console output returns summary information at the end of replay, but no other replay statistics are available.</span></span>

 <span data-ttu-id="b6b55-123">**-s** *target_server* especifica a instância de destino da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qual a carga de trabalho distribuída deve ser reproduzida.</span><span class="sxs-lookup"><span data-stu-id="b6b55-123">**-s** *target_server* Specifies the target instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that the distributed workload should be replayed against.</span></span> <span data-ttu-id="b6b55-124">Você deve especificar esse parâmetro no formato **server_name[\nome da instância]** .</span><span class="sxs-lookup"><span data-stu-id="b6b55-124">You must specify this parameter in the format **server_name[\instance name]**.</span></span>

 <span data-ttu-id="b6b55-125">Você não pode usar "`localhost`" ou "`.`" como o servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="b6b55-125">You cannot use "`localhost`" or "`.`" as the target server.</span></span>

 <span data-ttu-id="b6b55-126">O parâmetro **-s** não será necessário se o elemento `<Server>` for especificado na seção `<ReplayOptions>` do arquivo de configuração de reprodução, `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="b6b55-126">The **-s** parameter is not required if the `<Server>` element is specified in the `<ReplayOptions>` section of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="b6b55-127">Se o parâmetro **-s** for usado, o elemento `<Server>` na seção `<ReplayOptions>` do arquivo de configuração de reprodução será ignorado.</span><span class="sxs-lookup"><span data-stu-id="b6b55-127">If the **-s** parameter is used, the `<Server>` element in the `<ReplayOptions>` section of the replay configuration file will be ignored.</span></span>

 <span data-ttu-id="b6b55-128">**-w** *clientes* este parâmetro obrigatório é uma lista separada por vírgulas (sem espaços) que especifica os nomes de computador dos clientes que devem participar do Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="b6b55-128">**-w** *clients* This required parameter is a comma-separated list (without spaces) that specifies the computer names of clients that should participate in the distributed replay.</span></span> <span data-ttu-id="b6b55-129">Endereços IP não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="b6b55-129">IP addresses are not allowed.</span></span> <span data-ttu-id="b6b55-130">Lembre-se de que os clientes já devem estar registrados com o controlador.</span><span class="sxs-lookup"><span data-stu-id="b6b55-130">Be aware that the clients must already be registered with the controller.</span></span>

> [!NOTE]
>  <span data-ttu-id="b6b55-131">Cada cliente efetua o registro com o controlador que é especificado no arquivo de configuração de cliente quando o serviço de cliente é iniciado.</span><span class="sxs-lookup"><span data-stu-id="b6b55-131">Each client registers with the controller that is specified in the client configuration file when the client service starts.</span></span>

 <span data-ttu-id="b6b55-132">**-c** *CONFIG_FILE* é o caminho completo do arquivo de configuração de reprodução; usado para especificar o local quando ele é armazenado em um local diferente.</span><span class="sxs-lookup"><span data-stu-id="b6b55-132">**-c** *config_file* Is the full path of the replay configuration file; used to specify the location when it is stored in a different location.</span></span>

 <span data-ttu-id="b6b55-133">O parâmetro **-c** não será necessário se você quiser usar os valores padrão do arquivo de configuração de reprodução, `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="b6b55-133">The **-c** parameter is not required if you want to use the default values of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="b6b55-134">**-f** *status_interval* especifica a frequência (em segundos) na qual o status será exibido.</span><span class="sxs-lookup"><span data-stu-id="b6b55-134">**-f** *status_interval* Specifies the frequency (in seconds) at which to display the status.</span></span>

 <span data-ttu-id="b6b55-135">Se **-f** não for especificado, o intervalo padrão será de 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="b6b55-135">If **-f** is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="b6b55-136">Exemplos</span><span class="sxs-lookup"><span data-stu-id="b6b55-136">Examples</span></span>
 <span data-ttu-id="b6b55-137">Neste exemplo, a reprodução distribuída deriva muito de seu comportamento a partir de um arquivo de configuração de reprodução modificado, `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="b6b55-137">In this example, the distributed replay derives much of its behavior from a modified replay configuration file, `DReplay.exe.replay.config`.</span></span>

-   <span data-ttu-id="b6b55-138">O parâmetro **-m** especifica que um computador denominado `controller1` atua como o controlador.</span><span class="sxs-lookup"><span data-stu-id="b6b55-138">The **-m** parameter specifies that a computer named `controller1` acts as the controller.</span></span> <span data-ttu-id="b6b55-139">O nome do computador deve ser especificado quando o serviço de controlador é executado em um computador diferente.</span><span class="sxs-lookup"><span data-stu-id="b6b55-139">The computer name must be specified when the controller service is running on a different computer.</span></span>

-   <span data-ttu-id="b6b55-140">O parâmetro **-d** especifica o local do arquivo intermediário no controlador, `c:\WorkingDir`.</span><span class="sxs-lookup"><span data-stu-id="b6b55-140">The **-d** parameter specifies the location of the intermediate file on the controller, `c:\WorkingDir`.</span></span>

-   <span data-ttu-id="b6b55-141">O parâmetro **-o** especifica que cada cliente especificado captura a atividade de reprodução e salva-a em um arquivo de rastreamento de resultado.</span><span class="sxs-lookup"><span data-stu-id="b6b55-141">The **-o** parameter specifies that each specified client capture the replay activity and save it to a result trace file.</span></span> <span data-ttu-id="b6b55-142">Observação: O elemento `<ResultTrace>` no arquivo de configuração pode ser usado para especificar se a contagem de linhas e o conjunto de resultados são registrados.</span><span class="sxs-lookup"><span data-stu-id="b6b55-142">Note: The `<ResultTrace>` element in the configuration file can be used to specify if row count and result set be recorded.</span></span>

-   <span data-ttu-id="b6b55-143">O parâmetro **-w** especifica que os computadores `client1` a `client4` participam como clientes na reprodução distribuída.</span><span class="sxs-lookup"><span data-stu-id="b6b55-143">The **-w** parameter specifies that computers `client1` through `client4` participate as clients in the distributed replay.</span></span>

-   <span data-ttu-id="b6b55-144">O parâmetro **-c** é usado para apontar para o arquivo de configuração modificado, `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="b6b55-144">The **-c** parameter is used to point to the modified configuration file, `DReplay.exe.replay.config`.</span></span>

-   <span data-ttu-id="b6b55-145">O parâmetro **-s** não é necessário porque o elemento `<Server>` é especificado no elemento `<ReplayOptions>` do arquivo de configuração de reprodução, `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="b6b55-145">The **-s** parameter is not required because the `<Server>` element is specified in the `<ReplayOptions>` element of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="b6b55-146">O estágio de reprodução de eventos é iniciado com a sintaxe a seguir, quando a ferramenta de administração é executada a partir de um computador diferente do controlador:</span><span class="sxs-lookup"><span data-stu-id="b6b55-146">The event replay stage is initiated with the following syntax, when the administration tool is run from a different computer than the controller:</span></span>

```
dreplay replay -m controller1 -d c:\WorkingDir -o -w client1,client2,client3,client4 -c c:\DReplay.exe.replay.config
```

 <span data-ttu-id="b6b55-147">Para especificar um modo de sequenciamento síncrono, o elemento `<SequencingMode>` do arquivo `DReplay.exe.replay.config` é definido igual ao valor `synchronization`.</span><span class="sxs-lookup"><span data-stu-id="b6b55-147">To specify a synchronous sequencing mode, the `<SequencingMode>` element of the `DReplay.exe.replay.config` file is set equal to the value `synchronization`.</span></span> <span data-ttu-id="b6b55-148">A seção `<ResultTrace>` do arquivo de configuração de reprodução é modificado para especificar que a contagem de linhas seja registrada.</span><span class="sxs-lookup"><span data-stu-id="b6b55-148">The `<ResultTrace>` section of the replay configuration file is modified to specify that row count be recorded.</span></span> <span data-ttu-id="b6b55-149">Essas alterações são mostradas no seguinte exemplo XML:</span><span class="sxs-lookup"><span data-stu-id="b6b55-149">These changes are shown in the following XML example:</span></span>

```
<?xml version='1.0'?>
<Options>
    <ReplayOptions>
        <Server>server_name\replay_target_instance</Server>
        <SequencingMode>synchronization</SequencingMode>
        <ConnectTimeScale></ConnectTimeScale>
        <ThinkTimeScale></ThinkTimeScale>
        <HealthmonInterval>60</HealthmonInterval>
        <QueryTimeout>3600</QueryTimeout>
        <ThreadsPerClient></ThreadsPerClient>
    </ReplayOptions>
    <OutputOptions>
        <ResultTrace>
            <RecordRowCount>Yes</RecordRowCount>
            <RecordResultSet>No</RecordResultSet>
        </ResultTrace>
    </OutputOptions>
</Options>
```

 <span data-ttu-id="b6b55-150">Para especificar um modo de sequenciamento de estresse, o elemento `<SequencingMode>` do arquivo `DReplay.exe.replay.config` é definido igual ao valor `stress`.</span><span class="sxs-lookup"><span data-stu-id="b6b55-150">To specify a stress sequencing mode, the `<SequencingMode>` element of the `DReplay.exe.replay.config` file is set equal to the value `stress`.</span></span> <span data-ttu-id="b6b55-151">Os elementos `<ConnectTimeScale>` e `<ThinkTimeScale>` são definidos como o valor `50` (para especificar 50 por cento).</span><span class="sxs-lookup"><span data-stu-id="b6b55-151">The `<ConnectTimeScale>` and `<ThinkTimeScale>` elements are set to the value `50` (to specify 50 percent).</span></span> <span data-ttu-id="b6b55-152">Para obter mais informações sobre tempo de conexão e tempo de raciocínio, consulte [Configure Distributed Replay](configure-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="b6b55-152">For more information about connect time and think time, see [Configure Distributed Replay](configure-distributed-replay.md).</span></span> <span data-ttu-id="b6b55-153">Essas alterações são mostradas no seguinte exemplo XML:</span><span class="sxs-lookup"><span data-stu-id="b6b55-153">These changes are shown in the following XML example:</span></span>

```
<?xml version='1.0'?>
<Options>
    <ReplayOptions>
        <Server>server_name\replay_target_instance_name</Server>
        <SequencingMode>stress</SequencingMode>
        <ConnectTimeScale>50</ConnectTimeScale>
        <ThinkTimeScale>50</ThinkTimeScale>
        <HealthmonInterval>60</HealthmonInterval>
        <QueryTimeout>3600</QueryTimeout>
        <ThreadsPerClient></ThreadsPerClient>
    </ReplayOptions>
    <OutputOptions>
        <ResultTrace>
            <RecordRowCount>Yes</RecordRowCount>
            <RecordResultSet>No</RecordResultSet>
        </ResultTrace>
    </OutputOptions>
</Options>
```

## <a name="permissions"></a><span data-ttu-id="b6b55-154">Permissões</span><span class="sxs-lookup"><span data-stu-id="b6b55-154">Permissions</span></span>
 <span data-ttu-id="b6b55-155">Você deve executar a ferramenta de administração como um usuário interativo, um usuário local ou uma conta de usuário de domínio.</span><span class="sxs-lookup"><span data-stu-id="b6b55-155">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="b6b55-156">Para usar uma conta de usuário local, a ferramenta de administração e o controlador devem estar em execução no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="b6b55-156">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="b6b55-157">Para saber mais, confira [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="b6b55-157">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b6b55-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b6b55-158">See Also</span></span>
 <span data-ttu-id="b6b55-159">[Reproduzir dados de rastreamento](replay-trace-data.md) [revisar os resultados da reprodução](review-the-replay-results.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [Configurar Distributed Replay](configure-distributed-replay.md) [SQL Server Distributed Replay Fórum](https://social.technet.microsoft.com/Forums/sl/sqldru/) [usando Distributed Replay para testar a carga sua SQL Server-parte 2](https://docs.microsoft.com/archive/blogs/msdn/mspfe/using-distributed-replay-to-load-test-your-sql-serverpart-2) [usando Distributed Replay para teste de carga sua SQL Server-parte 1](https://docs.microsoft.com/archive/blogs/batuhanyildiz/using-distributed-replay-to-load-test-your-sql-serverpart-1)</span><span class="sxs-lookup"><span data-stu-id="b6b55-159">[Replay Trace Data](replay-trace-data.md) [Review the Replay Results](review-the-replay-results.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [Configure Distributed Replay](configure-distributed-replay.md) [SQL Server Distributed Replay Forum](https://social.technet.microsoft.com/Forums/sl/sqldru/) [Using Distributed Replay to Load Test Your SQL Server - Part 2](https://docs.microsoft.com/archive/blogs/msdn/mspfe/using-distributed-replay-to-load-test-your-sql-serverpart-2) [Using Distributed Replay to Load Test Your SQL Server - Part 1](https://docs.microsoft.com/archive/blogs/batuhanyildiz/using-distributed-replay-to-load-test-your-sql-serverpart-1)</span></span>


