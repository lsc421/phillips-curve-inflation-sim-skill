"""
菲利普斯曲线通胀模拟 skill菲利普斯曲线通胀模拟技能
课程：货币银行学
功能：模拟失业率与通货膨胀率的菲利普斯曲线关系，绘图输出
"""
import numpy as np导入 numpy 作为 np
import matplotlib.pyplot as plt导入 matplotlib.pyplot 作为 plt

def phillips_curve_sim():
    # 菲利普斯曲线 π = π_e - α(u-u_n)
    np.random.seed(2026)
    u_n = 4.0 #自然失业率%
    alpha = 0.75
    pi_e = 2.0 #预期通胀

    u_list = np.linspace(2, 8, 60)
    pi_list = pi_e - alpha * (u_list - u_n) + np.random.normal(0,0.25,len(u_list))

    plt.rcParams["font.sans-serif"]=["SimHei"]
    plt.figure(figsize=(8,5))
    plt.plot(u_list, pi_list, c="#c82423", lw=2)
    plt.title("菲利普斯曲线：失业率 — 通货膨胀率")
    plt.xlabel("失业率(%)")
    plt.ylabel("通胀率(%)")
    plt.grid(alpha=0.3)
    plt.savefig("phillips_plot.png")
    plt.show()
    print("✅菲利普斯曲线模拟完成，图像已保存")

if __name__ == "__main__":如果__名称__ == "__主程序__":
    phillips_curve_sim()菲利普斯曲线模拟()
