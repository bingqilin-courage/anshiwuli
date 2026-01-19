# anshiwuli
高中学科资料下载
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>安老师物理资料下载中心</title>
    <meta name="description" content="高中物理学习资料免费下载 - 课件、习题、视频、试卷">
    <link rel="stylesheet" href="css/style.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+SC:wght@300;400;500;700&display=swap" rel="stylesheet">
    <link rel="icon" type="image/x-icon" href="favicon.ico">
    <style>
        /* 内联基础样式防止加载问题 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Noto Sans SC', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }
    </style>
</head>
<body>
    <!-- 导航栏 -->
    <nav class="navbar">
        <div class="container">
            <div class="logo">
                <i class="fas fa-atom"></i>
                <span>安老师物理资料库</span>
            </div>
            <div class="nav-info">
                <span class="update-time">
                    <i class="far fa-clock"></i> 最后更新: 2024年1月
                </span>
            </div>
        </div>
    </nav>

    <!-- 顶部统计 -->
    <div class="stats-bar">
        <div class="container">
            <div class="stats">
                <div class="stat-item">
                    <i class="fas fa-file-alt"></i>
                    <div>
                        <span class="stat-number" data-count="156">0</span>
                        <span class="stat-label">个资料文件</span>
                    </div>
                </div>
                <div class="stat-item">
                    <i class="fas fa-download"></i>
                    <div>
                        <span class="stat-number" data-count="8924">0</span>
                        <span class="stat-label">次下载</span>
                    </div>
                </div>
                <div class="stat-item">
                    <i class="fas fa-folder-open"></i>
                    <div>
                        <span class="stat-number" data-count="12">0</span>
                        <span class="stat-label">个分类</span>
                    </div>
                </div>
                <div class="stat-item">
                    <i class="fas fa-hdd"></i>
                    <div>
                        <span class="stat-number" data-count="3.2">0</span>
                        <span class="stat-label">GB 总大小</span>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- 搜索和筛选 -->
    <div class="filters-section">
        <div class="container">
            <!-- 搜索框 -->
            <div class="search-box">
                <i class="fas fa-search"></i>
                <input type="text" id="searchInput" placeholder="搜索资料名称、关键词...">
                <button id="searchBtn">搜索</button>
            </div>
            
            <!-- 分类筛选 -->
            <div class="category-filters">
                <div class="filter-title">
                    <i class="fas fa-filter"></i> 分类筛选:
                </div>
                <div class="filter-tags">
                    <button class="filter-tag active" data-category="all">全部资料</button>
                    <button class="filter-tag" data-category="力学">力学</button>
                    <button class="filter-tag" data-category="电磁学">电磁学</button>
                    <button class="filter-tag" data-category="光学">光学</button>
                    <button class="filter-tag" data-category="热学">热学</button>
                    <button class="filter-tag" data-category="近代物理">近代物理</button>
                    <button class="filter-tag" data-category="实验">实验</button>
                    <button class="filter-tag" data-category="试题">试题试卷</button>
                </div>
            </div>
            
            <!-- 类型筛选 -->
            <div class="type-filters">
                <div class="filter-title">
                    <i class="fas fa-file"></i> 文件类型:
                </div>
                <div class="type-tags">
                    <button class="type-tag" data-type="all">全部</button>
                    <button class="type-tag" data-type="pdf">
                        <i class="fas fa-file-pdf"></i> PDF
                    </button>
                    <button class="type-tag" data-type="ppt">
                        <i class="fas fa-file-powerpoint"></i> PPT
                    </button>
                    <button class="type-tag" data-type="word">
                        <i class="fas fa-file-word"></i> Word
                    </button>
                    <button class="type-tag" data-type="video">
                        <i class="fas fa-file-video"></i> 视频
                    </button>
                    <button class="type-tag" data-type="zip">
                        <i class="fas fa-file-archive"></i> 压缩包
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- 主内容区 -->
    <main class="container">
        <!-- 文件列表 -->
        <div class="files-section">
            <div class="section-header">
                <h2><i class="fas fa-download"></i> 资料下载列表</h2>
                <div class="sort-options">
                    <span>排序:</span>
                    <select id="sortSelect">
                        <option value="name">按名称</option>
                        <option value="date">按日期</option>
                        <option value="size">按大小</option>
                        <option value="downloads">按下载量</option>
                    </select>
                </div>
            </div>
            
            <!-- 文件列表容器 -->
            <div id="filesList" class="files-list">
                <!-- 文件卡片会通过JavaScript动态生成 -->
            </div>
            
            <!-- 分页 -->
            <div class="pagination">
                <button class="page-btn" id="prevPage">
                    <i class="fas fa-chevron-left"></i> 上一页
                </button>
                <div class="page-numbers" id="pageNumbers"></div>
                <button class="page-btn" id="nextPage">
                    下一页 <i class="fas fa-chevron-right"></i>
                </button>
            </div>
        </div>
    </main>

    <!-- 底部信息 -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3><i class="fas fa-info-circle"></i> 使用说明</h3>
                    <ul>
                        <li>所有资料免费下载，仅供学习使用</li>
                        <li>建议使用电脑下载大文件</li>
                        <li>PDF文件可用Adobe Reader打开</li>
                        <li>如有问题，请检查文件格式</li>
                    </ul>
                </div>
                
                <div class="footer-section">
                    <h3><i class="fas fa-shield-alt"></i> 安全提示</h3>
                    <ul>
                        <li>所有文件已通过安全扫描</li>
                        <li>下载后请先查杀病毒</li>
                        <li>请勿用于商业用途</li>
                        <li>尊重版权，传播知识</li>
                    </ul>
                </div>
                
                <div class="footer-section">
                    <h3><i class="fas fa-download"></i> 下载帮助</h3>
                    <ul>
                        <li>直接点击文件名下载</li>
                        <li>右键点击可选择"另存为"</li>
                        <li>大文件建议使用下载工具</li>
                        <li>无法下载时请刷新页面</li>
                    </ul>
                </div>
            </div>
            
            <div class="copyright">
                <p>© 2024 安老师物理资料库 | 本网站基于GitHub Pages构建</p>
                <p class="hint">
                    <i class="fas fa-exclamation-circle"></i>
                    提示：如需最新资料，请关注班级通知
                </p>
            </div>
        </div>
    </footer>

    <!-- JavaScript -->
    <script src="js/main.js"></script>
    
    <!-- 内联JavaScript作为备用 -->
    <script>
        // 基础数据（实际使用时可替换为真实的文件数据）
        const sampleFiles = [
            {
                id: 1,
                name: "高一物理必修一知识点总结.pdf",
                category: "力学",
                type: "pdf",
                size: "2.4MB",
                date: "2023-09-15",
                downloads: 1248,
                description: "必修一全册知识点梳理，含典型例题",
                url: "materials/力学/高一物理必修一知识点总结.pdf"
            },
            {
                id: 2,
                name: "牛顿运动定律专题训练.docx",
                category: "力学",
                type: "word",
                size: "1.8MB",
                date: "2023-10-20",
                downloads: 892,
                description: "牛顿三定律专项练习题，附详细解答",
                url: "materials/力学/牛顿运动定律专题训练.docx"
            },
            {
                id: 3,
                name: "电场强度与电势差讲解.pptx",
                category: "电磁学",
                type: "ppt",
                size: "4.2MB",
                date: "2023-11-05",
                downloads: 756,
                description: "电场概念讲解PPT，含动画演示",
                url: "materials/电磁学/电场强度与电势差讲解.pptx"
            },
            {
                id: 4,
                name: "电路分析习题集.zip",
                category: "电磁学",
                type: "zip",
                size: "8.5MB",
                date: "2023-10-28",
                downloads: 642,
                description: "直流电路、交流电路综合习题",
                url: "materials/电磁学/电路分析习题集.zip"
            },
            {
                id: 5,
                name: "几何光学成像规律.pdf",
                category: "光学",
                type: "pdf",
                size: "3.1MB",
                date: "2023-09-30",
                downloads: 534,
                description: "透镜成像公式推导及应用",
                url: "materials/光学/几何光学成像规律.pdf"
            },
            {
                id: 6,
                name: "热力学定律教学视频.mp4",
                category: "热学",
                type: "video",
                size: "156MB",
                date: "2023-11-12",
                downloads: 487,
                description: "热力学第一、第二定律讲解视频",
                url: "materials/热学/热力学定律教学视频.mp4"
            },
            {
                id: 7,
                name: "近代物理发展简史.doc",
                category: "近代物理",
                type: "word",
                size: "1.2MB",
                date: "2023-10-10",
                downloads: 398,
                description: "量子力学与相对论发展历程",
                url: "materials/近代物理/近代物理发展简史.doc"
            },
            {
                id: 8,
                name: "物理实验操作手册.pdf",
                category: "实验",
                type: "pdf",
                size: "5.6MB",
                date: "2023-11-18",
                downloads: 721,
                description: "高中物理必做实验详细步骤",
                url: "materials/实验/物理实验操作手册.pdf"
            },
            {
                id: 9,
                name: "2023高考物理模拟试题.zip",
                category: "试题",
                type: "zip",
                size: "12.3MB",
                date: "2023-11-25",
                downloads: 1124,
                description: "最新高考模拟题，含答案解析",
                url: "materials/试题/2023高考物理模拟试题.zip"
            },
            {
                id: 10,
                name: "动量守恒定律专题.pptx",
                category: "力学",
                type: "ppt",
                size: "3.8MB",
                date: "2023-10-15",
                downloads: 615,
                description: "动量守恒典型例题分析",
                url: "materials/力学/动量守恒定律专题.pptx"
            },
            {
                id: 11,
                name: "电磁感应现象实验指导.pdf",
                category: "电磁学",
                type: "pdf",
                size: "2.9MB",
                date: "2023-11-08",
                downloads: 432,
                description: "法拉第电磁感应实验操作指南",
                url: "materials/电磁学/电磁感应现象实验指导.pdf"
            },
            {
                id: 12,
                name: "光学仪器原理与使用.doc",
                category: "光学",
                type: "word",
                size: "2.1MB",
                date: "2023-10-22",
                downloads: 329,
                description: "显微镜、望远镜等光学仪器原理",
                url: "materials/光学/光学仪器原理与使用.doc"
            }
        ];

        // 初始化变量
        let allFiles = [...sampleFiles];
        let currentPage = 1;
        const itemsPerPage = 8;
        let currentCategory = 'all';
        let currentType = 'all';
        let currentSearch = '';
        let currentSort = 'name';

        // DOM加载完成后执行
        document.addEventListener('DOMContentLoaded', function() {
            initializePage();
            setupEventListeners();
            renderFiles();
        });
    </script>
</body>
</html>
