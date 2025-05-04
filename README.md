 product_info = self.products[self.current_selection]
        change = self.inserted_money - product_info["price"]
        
        # 更新库存
        product_info["stock"] -= 1
        
        # 找零
        if change > 0:
            print(f"找零: ¥{change:.1f}")
            self.print_change(change)
        
        print(f"出货: {self.current_selection} 🥤")
        print("感谢您的购买!")
        
        # 重置状态
        self.inserted_money = 0.0
        self.current_selection = None
        return True
