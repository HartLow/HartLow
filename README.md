"""
Script tạo các file SVG đẹp mắt cho GitHub Profile
Tạo banner, animated text, và các hiệu ứng gradient
"""

def create_banner_svg(username="HartLow", filename="HartLow.svg"):
    """Tạo banner với gradient và animation đẹp mắt"""
    svg_content = f'''<svg width="1200" height="300" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <!-- Gradient nền -->
    <linearGradient id="grad1" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#667eea;stop-opacity:1">
        <animate attributeName="stop-color" values="#667eea;#764ba2;#f093fb;#667eea" dur="8s" repeatCount="indefinite"/>
      </stop>
      <stop offset="100%" style="stop-color:#764ba2;stop-opacity:1">
        <animate attributeName="stop-color" values="#764ba2;#f093fb;#667eea;#764ba2" dur="8s" repeatCount="indefinite"/>
      </stop>
    </linearGradient>
    
    <!-- Gradient cho text -->
    <linearGradient id="textGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#ffffff;stop-opacity:1"/>
      <stop offset="50%" style="stop-color:#a8edea;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#fed6e3;stop-opacity:1"/>
    </linearGradient>
    
    <!-- Filter cho shadow -->
    <filter id="shadow" x="-50%" y="-50%" width="200%" height="200%">
      <feGaussianBlur in="SourceAlpha" stdDeviation="3"/>
      <feOffset dx="2" dy="2" result="offsetblur"/>
      <feComponentTransfer>
        <feFuncA type="linear" slope="0.5"/>
      </feComponentTransfer>
      <feMerge>
        <feMergeNode/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>
  
  <!-- Nền gradient -->
  <rect width="1200" height="300" fill="url(#grad1)"/>
  
  <!-- Các hình tròn trang trí -->
  <circle cx="100" cy="50" r="30" fill="#ffffff" opacity="0.1">
    <animate attributeName="cy" values="50;280;50" dur="15s" repeatCount="indefinite"/>
  </circle>
  <circle cx="300" cy="250" r="40" fill="#ffffff" opacity="0.1">
    <animate attributeName="cy" values="250;20;250" dur="12s" repeatCount="indefinite"/>
  </circle>
  <circle cx="800" cy="100" r="35" fill="#ffffff" opacity="0.1">
    <animate attributeName="cy" values="100;260;100" dur="18s" repeatCount="indefinite"/>
  </circle>
  <circle cx="1000" cy="200" r="25" fill="#ffffff" opacity="0.1">
    <animate attributeName="cy" values="200;50;200" dur="10s" repeatCount="indefinite"/>
  </circle>
  
  <!-- Text chính -->
  <text x="600" y="120" font-family="'Arial Black', sans-serif" font-size="72" font-weight="bold" 
        text-anchor="middle" fill="url(#textGrad)" filter="url(#shadow)">
    {username}
    <animate attributeName="opacity" values="1;0.8;1" dur="3s" repeatCount="indefinite"/>
  </text>
  
  <!-- Subtitle -->
  <text x="600" y="170" font-family="Arial, sans-serif" font-size="24" 
        text-anchor="middle" fill="#ffffff" opacity="0.9">
    💻 Developer | 🎨 Designer | 🚀 Creator
  </text>
  
  <!-- Quote -->
  <text x="600" y="220" font-family="'Courier New', monospace" font-size="18" 
        text-anchor="middle" fill="#ffffff" opacity="0.8" font-style="italic">
    "Code with passion, create with heart"
  </text>
  
  <!-- Decorative lines -->
  <line x1="200" y1="250" x2="1000" y2="250" stroke="#ffffff" stroke-width="2" opacity="0.3">
    <animate attributeName="x1" values="200;250;200" dur="4s" repeatCount="indefinite"/>
    <animate attributeName="x2" values="1000;950;1000" dur="4s" repeatCount="indefinite"/>
  </line>
</svg>'''
    
    with open(filename, 'w', encoding='utf-8') as f:
        f.write(svg_content)
    print(f"✅ Đã tạo {filename}")


def create_profile_night_view(username="HartLow", filename="profile-night-view.svg"):
    """Tạo banner night view với hiệu ứng sao và mặt trăng"""
    svg_content = f'''<svg width="1200" height="400" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <!-- Gradient bầu trời đêm -->
    <linearGradient id="nightSky" x1="0%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" style="stop-color:#0f2027;stop-opacity:1"/>
      <stop offset="50%" style="stop-color:#203a43;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#2c5364;stop-opacity:1"/>
    </linearGradient>
    
    <!-- Gradient mặt trăng -->
    <radialGradient id="moon">
      <stop offset="0%" style="stop-color:#ffd89b;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#19547b;stop-opacity:0.3"/>
    </radialGradient>
    
    <!-- Filter cho glow effect -->
    <filter id="glow">
      <feGaussianBlur stdDeviation="2.5" result="coloredBlur"/>
      <feMerge>
        <feMergeNode in="coloredBlur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>
  
  <!-- Nền bầu trời đêm -->
  <rect width="1200" height="400" fill="url(#nightSky)"/>
  
  <!-- Các ngôi sao nhấp nháy -->
  <circle cx="100" cy="80" r="2" fill="#ffffff">
    <animate attributeName="opacity" values="1;0.3;1" dur="2s" repeatCount="indefinite"/>
  </circle>
  <circle cx="250" cy="120" r="1.5" fill="#ffffff">
    <animate attributeName="opacity" values="0.3;1;0.3" dur="3s" repeatCount="indefinite"/>
  </circle>
  <circle cx="400" cy="60" r="2" fill="#ffffff">
    <animate attributeName="opacity" values="1;0.5;1" dur="2.5s" repeatCount="indefinite"/>
  </circle>
  <circle cx="550" cy="100" r="1.5" fill="#ffffff">
    <animate attributeName="opacity" values="0.5;1;0.5" dur="1.8s" repeatCount="indefinite"/>
  </circle>
  <circle cx="700" cy="70" r="2" fill="#ffffff">
    <animate attributeName="opacity" values="1;0.3;1" dur="2.2s" repeatCount="indefinite"/>
  </circle>
  <circle cx="850" cy="90" r="1.5" fill="#ffffff">
    <animate attributeName="opacity" values="0.3;1;0.3" dur="2.8s" repeatCount="indefinite"/>
  </circle>
  <circle cx="1000" cy="110" r="2" fill="#ffffff">
    <animate attributeName="opacity" values="1;0.5;1" dur="2s" repeatCount="indefinite"/>
  </circle>
  <circle cx="1100" cy="75" r="1.5" fill="#ffffff">
    <animate attributeName="opacity" values="0.5;1;0.5" dur="2.6s" repeatCount="indefinite"/>
  </circle>
  
  <!-- Mặt trăng -->
  <circle cx="1000" cy="100" r="60" fill="url(#moon)" filter="url(#glow)">
    <animate attributeName="opacity" values="0.8;1;0.8" dur="5s" repeatCount="indefinite"/>
  </circle>
  
  <!-- Text chính với hiệu ứng glow -->
  <text x="600" y="220" font-family="'Arial Black', sans-serif" font-size="64" font-weight="bold" 
        text-anchor="middle" fill="#ffffff" filter="url(#glow)">
    {username}
  </text>
  
  <!-- Animated subtitle -->
  <text x="600" y="280" font-family="Arial, sans-serif" font-size="22" 
        text-anchor="middle" fill="#64b5f6">
    ✨ Coding under the stars ✨
    <animate attributeName="fill" values="#64b5f6;#81c784;#ffb74d;#64b5f6" dur="6s" repeatCount="indefinite"/>
  </text>
  
  <!-- Quote -->
  <text x="600" y="330" font-family="'Courier New', monospace" font-size="16" 
        text-anchor="middle" fill="#b0bec5" font-style="italic">
    "Dream big, code bigger"
  </text>
</svg>'''
    
    with open(filename, 'w', encoding='utf-8') as f:
        f.write(svg_content)
    print(f"✅ Đã tạo {filename}")


def create_animated_hello(filename="hello.svg"):
    """Tạo animated hello text với typing effect"""
    svg_content = '''<svg width="800" height="200" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="helloGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#FF6B6B;stop-opacity:1">
        <animate attributeName="stop-color" values="#FF6B6B;#4ECDC4;#45B7D1;#FF6B6B" dur="5s" repeatCount="indefinite"/>
      </stop>
      <stop offset="50%" style="stop-color:#4ECDC4;stop-opacity:1">
        <animate attributeName="stop-color" values="#4ECDC4;#45B7D1;#FF6B6B;#4ECDC4" dur="5s" repeatCount="indefinite"/>
      </stop>
      <stop offset="100%" style="stop-color:#45B7D1;stop-opacity:1">
        <animate attributeName="stop-color" values="#45B7D1;#FF6B6B;#4ECDC4;#45B7D1" dur="5s" repeatCount="indefinite"/>
      </stop>
    </linearGradient>
    
    <filter id="textShadow">
      <feDropShadow dx="2" dy="2" stdDeviation="2" flood-color="#000000" flood-opacity="0.3"/>
    </filter>
  </defs>
  
  <rect width="800" height="200" fill="#1a1a2e"/>
  
  <!-- Animated circles background -->
  <circle cx="100" cy="100" r="50" fill="#16213e" opacity="0.3">
    <animate attributeName="r" values="50;60;50" dur="3s" repeatCount="indefinite"/>
  </circle>
  <circle cx="700" cy="100" r="40" fill="#0f3460" opacity="0.3">
    <animate attributeName="r" values="40;50;40" dur="4s" repeatCount="indefinite"/>
  </circle>
  
  <!-- Main text -->
  <text x="400" y="100" font-family="'Arial Black', sans-serif" font-size="72" 
        text-anchor="middle" fill="url(#helloGrad)" filter="url(#textShadow)">
    👋 Hello!
  </text>
  
  <!-- Subtitle -->
  <text x="400" y="145" font-family="Arial, sans-serif" font-size="24" 
        text-anchor="middle" fill="#e94560">
    Welcome to my GitHub Profile
    <animate attributeName="opacity" values="0.7;1;0.7" dur="2s" repeatCount="indefinite"/>
  </text>
</svg>'''
    
    with open(filename, 'w', encoding='utf-8') as f:
        f.write(svg_content)
    print(f"✅ Đã tạo {filename}")


def create_intro_image(username="HartLow", filename="img.svg"):
    """Tạo intro image với hiệu ứng particle"""
    svg_content = f'''<svg width="1000" height="250" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="introGrad" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#f857a6;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#ff5858;stop-opacity:1"/>
    </linearGradient>
    
    <linearGradient id="textIntroGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#ffffff;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#ffeaa7;stop-opacity:1"/>
    </linearGradient>
    
    <filter id="glowEffect">
      <feGaussianBlur stdDeviation="3" result="coloredBlur"/>
      <feMerge>
        <feMergeNode in="coloredBlur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>
  
  <!-- Background -->
  <rect width="1000" height="250" fill="url(#introGrad)"/>
  
  <!-- Animated particles -->
  <circle cx="50" cy="50" r="3" fill="#ffffff" opacity="0.6">
    <animate attributeName="cx" values="50;950;50" dur="20s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="50;200;50" dur="15s" repeatCount="indefinite"/>
  </circle>
  <circle cx="200" cy="150" r="4" fill="#ffffff" opacity="0.5">
    <animate attributeName="cx" values="200;800;200" dur="18s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="150;100;150" dur="12s" repeatCount="indefinite"/>
  </circle>
  <circle cx="500" cy="80" r="3.5" fill="#ffffff" opacity="0.7">
    <animate attributeName="cx" values="500;100;500" dur="22s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="80;180;80" dur="14s" repeatCount="indefinite"/>
  </circle>
  <circle cx="800" cy="180" r="4" fill="#ffffff" opacity="0.6">
    <animate attributeName="cx" values="800;150;800" dur="19s" repeatCount="indefinite"/>
    <animate attributeName="cy" values="180;60;180" dur="16s" repeatCount="indefinite"/>
  </circle>
  
  <!-- Main text -->
  <text x="500" y="110" font-family="'Arial Black', sans-serif" font-size="56" font-weight="bold"
        text-anchor="middle" fill="url(#textIntroGrad)" filter="url(#glowEffect)">
    Hi there, I'm {username}! 👨‍💻
  </text>
  
  <!-- Subtitle -->
  <text x="500" y="160" font-family="Arial, sans-serif" font-size="22"
        text-anchor="middle" fill="#ffffff" opacity="0.95">
    🚀 Full Stack Developer | 💡 Problem Solver | 🎯 Tech Enthusiast
  </text>
  
  <!-- Footer text -->
  <text x="500" y="210" font-family="'Courier New', monospace" font-size="16"
        text-anchor="middle" fill="#ffffff" opacity="0.8">
    "Turning ideas into reality, one line of code at a time"
  </text>
</svg>'''
    
    with open(filename, 'w', encoding='utf-8') as f:
        f.write(svg_content)
    print(f"✅ Đã tạo {filename}")


def main():
    """Tạo tất cả các file SVG"""
    print("🎨 Bắt đầu tạo các file SVG đẹp mắt...\n")
    
    username = "HartLow"
    
    # Tạo các file SVG
    create_banner_svg(username, "HartLow.svg")
    create_profile_night_view(username, "profile-night-view.svg")
    create_animated_hello("hello.svg")
    create_intro_image(username, "img.svg")
    
    print("\n🎉 Hoàn thành! Đã tạo tất cả các file SVG:")
    print("   - HartLow.svg (Banner chính)")
    print("   - profile-night-view.svg (Night view)")
    print("   - hello.svg (Animated hello)")
    print("   - img.svg (Intro image)")
    print("\n💡 Lưu ý: Upload các file này lên GitHub repository của bạn!")


if __name__ == "__main__":
    main()
