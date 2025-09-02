<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>インタラクティブ実験報告：〇〇の分析</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Noto+Sans+JP:wght@400;500;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Warm Neutrals -->
    <!-- Application Structure Plan: 静的な論文形式を脱却し、ユーザーが関心のある項目（概要、実験方法、結果と考察）へ直接アクセスできるタブ形式のナビゲーション構造を採用しました。これにより、長いスクロールなしに必要な情報を効率的に探索できます。中心となる「結果と考察」セクションでは、静的な画像をインタラクティブなグラフに置き換えることで、データへの深い洞察を促します。この非線形な構造は、情報を消費する際の認知負荷を軽減し、ユーザーエンゲージメントを高めることを目的としています。 -->
    <!-- Visualization & Content Choices: 報告書の情報に対し、最適なインタラクティブ要素を選択しました。緒言と要約は「概要」としてまとめ、平易なテキストで提示（目標：通知）。実験方法は手順の再現性を重視し、構造化されたリストで整理（目標：整理）。中心的な「結果」の図は、静的な画像からChart.js（Canvas）による動的な散布図へ変更。ユーザーがデータポイントをホバーしたり、データセットを切り替えたりすることで、〇〇と△△の関係性を能動的に探求できるようにしました（目標：関係性の可視化、比較）。考察や結論は、主要なポイントを強調するテキストブロックとして配置しました。 -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Noto Sans JP', 'Inter', sans-serif;
            background-color: #f8f7f2;
        }
        .active-tab {
            background-color: #e2e8f0;
            color: #1e293b;
            font-weight: 600;
        }
        .content-section {
            display: none;
        }
        .content-section.active {
            display: block;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
            height: 50vh;
            max-height: 450px;
        }
    </style>
</head>
<body class="text-slate-800">
    <div class="min-h-screen flex flex-col lg:flex-row">
        <aside class="w-full lg:w-64 bg-white/80 backdrop-blur-sm border-b lg:border-r border-slate-200 p-4 lg:p-6 lg:sticky lg:top-0 lg:h-screen">
            <div class="mb-8">
                <h1 class="text-xl font-bold text-slate-900">サンプル実験報告</h1>
                <p class="text-sm text-slate-600 mt-1">〇〇の分析</p>
                <p class="text-xs text-slate-500 mt-2">著者: あなたの名前</p>
                <p class="text-xs text-slate-500 mt-1">報告日: 2025年09月02日</p>
            </div>
            <nav>
                <ul class="space-y-2">
                    <li><a href="#overview" class="nav-link block w-full text-left px-4 py-2 text-sm rounded-md text-slate-700 hover:bg-slate-200 transition-colors active-tab">概要</a></li>
                    <li><a href="#methods" class="nav-link block w-full text-left px-4 py-2 text-sm rounded-md text-slate-700 hover:bg-slate-200 transition-colors">実験方法</a></li>
                    <li><a href="#results" class="nav-link block w-full text-left px-4 py-2 text-sm rounded-md text-slate-700 hover:bg-slate-200 transition-colors">結果と考察</a></li>
                    <li><a href="#conclusion" class="nav-link block w-full text-left px-4 py-2 text-sm rounded-md text-slate-700 hover:bg-slate-200 transition-colors">結論と補足</a></li>
                </ul>
            </nav>
        </aside>
        <main class="flex-1 p-4 sm:p-6 md:p-8">
            <div id="overview" class="content-section active">
                <div class="bg-white p-6 rounded-lg shadow-sm">
                    <h2 class="text-2xl font-bold mb-4 border-b pb-2">要約</h2>
                    <div class="prose max-w-none text-slate-700">
                        <p>本研究では、[研究対象]における[特定現象]のメカニズムを解明することを目的とした。 [実験手法の概要]を用いて[主要なパラメータ]を測定した結果、[主要な発見]が明らかになった。 この結果は、[結果が示唆すること]を示唆しており、[分野]における新たな知見を提供するものである。</p>
                    </div>
                </div>
                <div class="bg-white p-6 rounded-lg shadow-sm mt-6">
                    <h2 class="text-2xl font-bold mb-4 border-b pb-2">1. 緒言 (Introduction)</h2>
                    <div class="prose max-w-none text-slate-700">
                        <p>ここに研究の背景を記述します。 なぜこの研究が必要なのか、どのような問題意識から出発したのかを説明してください。 先行研究に触れ、本研究の位置づけを明確にすることも重要です。 最後に、本研究の目的を具体的に述べます。</p>
                    </div>
                </div>
            </div>
            <div id="methods" class="content-section">
                 <div class="bg-white p-6 rounded-lg shadow-sm">
                    <h2 class="text-2xl font-bold mb-4 border-b pb-2">2. 実験方法 (Methods)</h2>
                    <div class="prose max-w-none text-slate-700">
                        <p>このセクションでは、実験の手順を他の研究者が再現できるように、具体的かつ詳細に記述します。</p>
                        <h3 class="text-xl font-semibold mt-6">2.1. 使用した装置</h3>
                        <ul class="list-disc list-inside mt-2 bg-slate-50 p-4 rounded-md">
                            <li>装置A (メーカー名, 型番)</li>
                            <li>装置B (メーカー名, 型番)</li>
                        </ul>
                        <h3 class="text-xl font-semibold mt-6">2.2. 実験手順</h3>
                        <ol class="list-decimal list-inside mt-2 space-y-2">
                            <li class="p-2 bg-slate-50 rounded-md">手順1を記述します。</li>
                            <li class="p-2 bg-slate-50 rounded-md">手順2を記述します。</li>
                            <li class="p-2 bg-slate-50 rounded-md">手順3を記述します。</li>
                        </ol>
                    </div>
                </div>
            </div>
            <div id="results" class="content-section">
                <div class="bg-white p-6 rounded-lg shadow-sm">
                    <h2 class="text-2xl font-bold mb-2 border-b pb-2">3. 結果 (Results)</h2>
                     <p class="text-slate-600 mb-4">実験によって得られた客観的なデータを提示します。下のグラフは〇〇と△△の関係性を示しており、データセットを切り替えて傾向を確認できます。</p>                    
                    <div class="chart-container mb-4">
                        <canvas id="experimentChart"></canvas>
                    </div>
                     <div class="flex justify-center items-center gap-2 mb-6">
                        <button id="data1Btn" class="px-4 py-2 text-sm font-medium text-white bg-slate-700 rounded-md hover:bg-slate-800 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-slate-500 transition-all">データセット 1</button>
                        <button id="data2Btn" class="px-4 py-2 text-sm font-medium text-slate-700 bg-slate-200 rounded-md hover:bg-slate-300 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-slate-500 transition-all">データセット 2</button>
                    </div>
                </div>
                <div class="bg-white p-6 rounded-lg shadow-sm mt-6">
                    <h2 class="text-2xl font-bold mb-4 border-b pb-2">4. 考察 (Discussion)</h2>
                    <div class="prose max-w-none text-slate-700">
                        <p>結果セクションで示したデータが何を意味するのかを考察します。緒言で述べた問題意識や仮説と関連付けて議論してください。先行研究の結果と比較し、共通点や相違点を明らかにすることも重要です。また、この実験の限界や、将来的な課題についても言及します。</p>
                    </div>
                </div>
            </div>
            <div id="conclusion" class="content-section">
                <div class="bg-white p-6 rounded-lg shadow-sm">
                    <h2 class="text-2xl font-bold mb-4 border-b pb-2">5. 結論 (Conclusion)</h2>
                    <div class="prose max-w-none text-slate-700">
                        <p>本研究で明らかになったことを簡潔にまとめます。要約と重複する部分もありますが、研究全体の締めくくりとして結論を明確に述べます。</p>
                    </div>
                </div>
                 <div class="bg-white p-6 rounded-lg shadow-sm mt-6">
                    <h2 class="text-2xl font-bold mb-4 border-b pb-2">6. 参考文献 & 7. 謝辞</h2>
                    <div class="prose max-w-none text-slate-700">
                         <h3 class="text-lg font-semibold mt-4">参考文献 (References)</h3>
                        <ol class="list-decimal list-inside text-sm">
                            <li>Author, A. A. (Year). <em>Title of work</em>. Publisher.</li>
                            <li>Author, B. B., & Author, C. C. (Year). Title of chapter. In D. D. Editor (Ed.), <em>Title of book</em> (pp. xx-xx). Publisher.</li>
                        </ol>
                        <h3 class="text-lg font-semibold mt-6">謝辞 (Acknowledgements)</h3>
                        <p>実験に協力していただいた方々や、助言をいただいた先生方への感謝を述べます。</p>
                    </div>
                </div>
            </div>
        </main>
    </div>
    <script>
        document.addEventListener('DOMContentLoaded', function () {
            const navLinks = document.querySelectorAll('.nav-link');
            const contentSections = document.querySelectorAll('.content-section');
            const setActiveTab = (hash) => {
                navLinks.forEach(link => {
                    if (link.getAttribute('href') === hash) {
                        link.classList.add('active-tab');
                    } else {
                        link.classList.remove('active-tab');
                    }
                });
                contentSections.forEach(section => {
                    if ('#' + section.id === hash) {
                        section.classList.add('active');
                    } else {
                        section.classList.remove('active');
                    }
                });
            };
            navLinks.forEach(link => {
                link.addEventListener('click', function (e) {
                    e.preventDefault();
                    const targetId = this.getAttribute('href');
                    setActiveTab(targetId);
                    window.location.hash = targetId;
                });
            });
            const initialHash = window.location.hash || '#overview';
            setActiveTab(initialHash);
            const generateData = (factor, count) => {
                return Array.from({ length: count }, (_, i) => ({
                    x: i * 2,
                    y: (i * factor) + (Math.random() * 10 - 5)
                }));
            };
            const data1 = generateData(1.5, 20);
            const data2 = generateData(-0.8, 20);
            const datasets = [
                {
                    label: 'データセット 1',
                    data: data1,
                    backgroundColor: 'rgba(59, 130, 246, 0.5)',
                    borderColor: 'rgba(59, 130, 246, 1)',
                    borderWidth: 2,
                    pointRadius: 5,
                    pointHoverRadius: 8
                },
                {
                    label: 'データセット 2',
                    data: data2,
                    backgroundColor: 'rgba(239, 68, 68, 0.5)',
                    borderColor: 'rgba(239, 68, 68, 1)',
                    borderWidth: 2,
                    pointRadius: 5,
                    pointHoverRadius: 8
                }
            ];
            const ctx = document.getElementById('experimentChart').getContext('2d');
            const experimentChart = new Chart(ctx, {
                type: 'scatter',
                data: {
                    datasets: [datasets[0]]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    scales: {
                        x: {
                            title: {
                                display: true,
                                text: '変数 〇〇',
                                font: { size: 14 }
                            }
                        },
                        y: {
                            title: {
                                display: true,
                                text: '変数 △△',
                                font: { size: 14 }
                            }
                        }
                    },
                    plugins: {
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    return `(〇〇: ${context.parsed.x.toFixed(2)}, △△: ${context.parsed.y.toFixed(2)})`;
                                }
                            }
                        },
                         legend: {
                            position: 'top',
                        },
                    }
                }
            });
            const data1Btn = document.getElementById('data1Btn');
            const data2Btn = document.getElementById('data2Btn');
            const updateChartData = (datasetIndex) => {
                experimentChart.data.datasets = [datasets[datasetIndex]];
                experimentChart.update();
                if(datasetIndex === 0) {
                    data1Btn.classList.add('bg-slate-700', 'text-white');
                    data1Btn.classList.remove('bg-slate-200', 'text-slate-700');
                    data2Btn.classList.add('bg-slate-200', 'text-slate-700');
                    data2Btn.classList.remove('bg-slate-700', 'text-white');
                } else {
                    data2Btn.classList.add('bg-slate-700', 'text-white');
                    data2Btn.classList.remove('bg-slate-200', 'text-slate-700');
                    data1Btn.classList.add('bg-slate-200', 'text-slate-700');
                    data1Btn.classList.remove('bg-slate-700', 'text-white');
                }
            }
            data1Btn.addEventListener('click', () => updateChartData(0));
            data2Btn.addEventListener('click', () => updateChartData(1));
            updateChartData(0);
        });
    </script>
</body>
</html>
